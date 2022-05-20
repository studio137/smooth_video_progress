Have you been here before: you created a video player using [video_player](https://pub.dev/packages/video_player),
but the progress bar updates way to infrequently and makes your UX look choppy?

Look no further than this package. It will make your video progress bars look smooooth ✨

## Check it out:
Since this is a GIF, the framerate is reduced, but rest assured that the bottom slider
animates at the same framerate as your app.

![Demo GIF](demo.gif)

## Features

- Build a smoothly interpolated progress bar for [video_player](https://pub.dev/packages/video_player)'s ``VideoPlayerController`` instances.
- Completely unopinianeted, build whatever you want design-wise
- Use it for progress bars, spinners, more accurate time displays, ...
## Getting started

Install the package. This package depends on [flutter_hooks](https://pub.dev/packages/flutter_hooks), because I use it for everything
anyway, check out the package if you don't know it, it makes life so much easier.

## Usage

Here is how you would build a simple slider for example:
```dart
Widget build(BuildContext context) {
  SmoothVideoProgress(
    controller: controller,
    builder: (context, position, duration, child) => Slider(
      onChangeStart: (_) => controller.pause(),
      onChangeEnd: (_) => controller.play(),
      onChanged: (value) =>
          controller.seekTo(Duration(milliseconds: value.toInt())),
      value: position.inMilliseconds.toDouble(),
      min: 0,
      max: duration.inMilliseconds.toDouble(),
    ),
  );
}
```

