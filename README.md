# Xamarin.DuGuLib
This is a Xamarin Lib of DuGu(Peefy) @(https://github.com/Peefy)

## Nuget
>Install-Package Xamarin.DuGuLib -Version 1.0.0.3

>Please add the nuget packet to Pcl Project, Android Project and iOS Project(three projects)

## How to use and init.

>In your Android project MainActivity.cs ,code as follow:

```c#
using System;

using Android.App;
using Android.Content.PM;
using Android.Runtime;
using Android.Views;
using Android.Widget;
using Android.OS;

namespace YourNamespace.Droid
{
    [Activity(Label = "AppName", Icon = "@drawable/icon", Theme = "@style/MainTheme", MainLauncher = true, ConfigurationChanges =            ConfigChanges.ScreenSize | ConfigChanges.Orientation)]
    public class MainActivity : global::Xamarin.Forms.Platform.Android.FormsAppCompatActivity
    {
        protected override void OnCreate(Bundle bundle)
        {
            TabLayoutResource = Resource.Layout.Tabbar;
            ToolbarResource = Resource.Layout.Toolbar;

            base.OnCreate(bundle);
            global::Xamarin.Forms.Forms.SetFlags("FastRenderers_Experimental");
            global::Xamarin.Forms.Forms.Init(this, bundle);

            DuGu.XFLib.Droid.ControlSet.Init();
            DuGu.XFLib.Droid.Services.AndroidToolBar.Init(Resource.Id.toolbar);

            LoadApplication(new App());
        }
    }
}
```

>In your iOS project AppDelegate.cs ,code as follow:

```c#
using System;
using System.Collections.Generic;
using System.Linq;

using Foundation;
using UIKit;

namespace YourNamespace.iOS
{
    [Register("AppDelegate")]
    public partial class AppDelegate : global::Xamarin.Forms.Platform.iOS.FormsApplicationDelegate
    {
        public override bool FinishedLaunching(UIApplication app, NSDictionary options)
        {
            global::Xamarin.Forms.Forms.Init();

            DuGu.XFLib.iOS.ControlSet.Init();

            LoadApplication(new App());

            return base.FinishedLaunching(app, options);
        }
    }
}
```

Then you can use the packet in your pcl project.

## Feature

* Animations
* Behaviors
* Binders
* Controls
* Effects
* Models
* Services
* ViewModels

### *Animations*

* FadeTo
* RotateTo
* ScaleTo 
* StoryBoard

These animations help you use animation in *XAML* file.

### *Behaviors*

* EventToCommandBehavior
* MaxLengthTextBehavior
* RadioBehaviorBehavior

### *Binders*

* AndroidToolBarBinder
* ListViewBinder
* TagBinder
* TapBinder

### *Controls*

* BottomTabView(Android UI and iOS UI are same)
* BindablePicker
* ButtonEx
* CarouseLayout
* DataPicker
* EntryEx
* FloatingActionButton
* ImageButton
* ImageEx
* LabelEx
* ListViewEx
* LoadingView
* Marquee
* NavigationPageEx
* Repeater
* ScrollViewEx
* StackedList
* TimePickerEx
* ToggleButton
* UniformGrid
* WebViewEx
* WrapLayout

### *Effects*

* KeyboardEnter
* Shadow

### *Model*

* BaseDataObject
* ExtendedBindableObject
* ObservableRangeCollection

###
### *Services*

Use DependencyService.Get<T> to get interface.For example :

```c#
DependencyService.Get<IScreen>().GetFullSize();
```
* IAndroidFinish
* IAndroidToolBar
* IKeyBoard
* IPicture
* IScreen
* IToast
* NavigationService(This is a class,not interface)

### *ViewModels*

* ListViewModelBase
* ViewModelBase

## Thanks
If you like it or it help you.Thanks for *fork* and *star*.

Thank you.






