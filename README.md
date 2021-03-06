# SpeedometerView

Simple speedometer-like gauge with needle for Android.

![speedometerview-v1](https://f.cloud.github.com/assets/1446492/2292440/175bd3a8-a059-11e3-8f1e-67624fc92349.png)

**Download:** [SpeedometerView-v1.0.1](https://github.com/ntoskrnl/SpeedometerView/releases/tag/SpeedometerView-v1.0.1)

## Usage


In your layout xml-file add SpeedometerView as shown:

```xml
<com.cardiomood.android.speedometer.SpeedometerView
    android:layout_height="wrap_content"
    android:layout_width="match_parent"
    android:padding="8dp"
    android:id="@+id/speedometer" />
```

Configure SpeedometerView:

```java
  private SpeedometerView speedometer;

  // Customize SpeedometerView
  speedometer = (SpeedometerView) v.findViewById(R.id.speedometer);
  
  // Add label converter
  speedometer.setLabelConverter(new SpeedometerView.LabelConverter() {
      @Override
      public String getLabelFor(double progress, double maxProgress) {
          return String.valueOf((int) Math.round(progress));
      }
  });
  
  // configure value range and ticks
  speedometer.setMaxSpeed(300);
  speedometer.setMajorTickStep(30);
  speedometer.setMinorTicks(2);
  
  // Configure value range colors
  speedometer.addColoredRange(30, 140, Color.GREEN);
  speedometer.addColoredRange(140, 180, Color.YELLOW);
  speedometer.addColoredRange(180, 400, Color.RED);

```

## Version History

**SpeedometerView 1.0.1**

- added attribute labelTextSize
- text is drawn in dp (looks the same on all screens now)
- fixed needle artifact
 
Download: [SpeedometerView-v1.0.1](https://github.com/ntoskrnl/SpeedometerView/releases/tag/SpeedometerView-v1.0.1)

**SpeedometerView 1.0**

Minimal Android SDK version: 9 (Android 2.3)

**Supported features**:
- Major and minor tick marks
- Custom labels
- Colored value ranges
- Animation of arrow (*requires Android API level 11+*)

Download: [SpeedometerView-v1.0](https://github.com/ntoskrnl/SpeedometerView/releases/tag/SpeedometerView-v1.0)
