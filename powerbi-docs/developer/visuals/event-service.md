---
title: Render events in Power BI visuals
description: Power BI visuals can notify Power BI that they're ready for export to PowerPoint or PDF.
author: KesemSharabi
ms.author: kesharab
ms.reviewer: rkarlin
ms.service: powerbi
ms.subservice: powerbi-custom-visuals
ms.topic: reference
ms.date: 05/18/2021
---

# Render events in Power BI visuals

In order to get a [visual certified](power-bi-custom-visuals-certified.md) is must support the *rendering events API*.

This API consists of three methods (`started`, `finished`, or `failed`) that should be called during rendering:

* `renderingStarted`: The Power BI visual code calls the `renderingStarted` method to indicate that the rendering process has started. **This method should always be called on the first line of the *update* method since that is where the rendering process begins**.

* `renderingFinished`: When rendering is completed successfully, the Power BI visual code calls the `renderingFinished` method to notify the listeners (primarily, *export to PDF* and *export to PowerPoint*) that the visual's image is ready for export. This should be the last line of code **executed** when the visual updates. This is usually, but not always, the last line of the update method.

* `renderingFailed`: If a problem occurs during the rendering process, the Power BI visual is doesn't render successfully. To notify the listeners that the rendering process hasn't been completed, the Power BI visual code should call the `renderingFailed` method. This method also provides an optional string to provide a reason for the failure.

## How to use the rendering events API

To call the rendering methods, you have to first import them from the *IVisualEventService*.

1. In your `visual.ts` file include the line:

    ```typescript
    import IVisualEventService = powerbi.extensibility.IVisualEventService;
    ```

2. In the `IVisual` class include the line:

    ```typescript
    private events: IVisualEventService;
    ```

3. In the `constructor` method of the `IVisual` class

    ```typescript
    this.events = options.host.eventService;
    ```

You can now call the methods
`this.events.renderingStarted(options);`,
`this.events.renderingFinished(options);`, and
`this.events.renderingFailed(options);` where appropriate in your *update* method.

## Example 1: Visual without animations

Here is an example of a simple visual that uses the *render events* API.

```typescript
    export class Visual implements IVisual {
        ...
        private events: IVisualEventService;
        ...

        constructor(options: VisualConstructorOptions) {
            ...
            this.events = options.host.eventService;
            ...
        }

        public update(options: VisualUpdateOptions) {
            this.events.renderingStarted(options);
            ...
            this.events.renderingFinished(options);
        }
```

## Example 2: Visual with animations

If the visual has animations or asynchronous functions for rendering, the `renderingFinished` method should be called after the animation or inside async function even if that is not the last line of the *update* method.

```typescript
    export class Visual implements IVisual {
        ...
        private events: IVisualEventService;
        private element: HTMLElement;
        ...

        constructor(options: VisualConstructorOptions) {
            ...
            this.events = options.host.eventService;
            this.element = options.element;
            ...
        }

        public update(options: VisualUpdateOptions) {
            this.events.renderingStarted(options);
            ...
            // Learn more at https://github.com/d3/d3-transition/blob/master/README.md#transition_end
            d3.select(this.element).transition().duration(100).style("opacity","0").end().then(() => {
                // renderingFinished called after transition end
                this.events.renderingFinished(options);
            });
        }
```

## Rendering events for visual certification

> [!NOTE]
> Support of rendering events is a requirement for visuals certification. Without this API your visual won't be approved by Partner Center for publication. For more information, see [certification requirements](power-bi-custom-visuals-certified.md#certification-requirements).
