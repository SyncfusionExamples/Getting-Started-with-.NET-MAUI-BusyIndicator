# Getting Started with .NET MAUI BusyIndicator (SfBusyIndicator)

This section provides a quick overview for working with the SfBusyIndicator for .NET MAUI. Walk through the entire process of creating a real world of this control.

## Creating an application using the .NET MAUI Busy Indicator
 1. Create a new .NET MAUI application in Visual Studio.
 2. Syncfusion .NET MAUI components are available on [nuget.org](https://www.nuget.org/). To add SfBusyIndicator to your project, open the NuGet package manager in Visual Studio, search for Syncfusion.Maui.Core and then install it.

## Register the handler

To use this control inside an application, you must register the handler for Syncfusion® core.

```C#

using Microsoft.Extensions.Logging;
using Syncfusion.Maui.Core.Hosting;

namespace BusyIndicatorGettingStarted
{
    public static class MauiProgram
    {
        public static MauiApp CreateMauiApp()
        {
            var builder = MauiApp.CreateBuilder();
            builder
                .UseMauiApp<App>()
                .ConfigureSyncfusionCore()
                .ConfigureFonts(fonts =>
                {
                    fonts.AddFont("OpenSans-Regular.ttf", "OpenSansRegular");
                    fonts.AddFont("OpenSans-Semibold.ttf", "OpenSansSemibold");
                });

#if DEBUG
    		builder.Logging.AddDebug();
#endif

            return builder.Build();
        }
    }
}

```

## Add a basic Busy Indicator
1. Import the control namespace `Syncfusion.Maui.Core` in XAML or C# code.
2. Initialize the [SfBusyIndicator](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Core.SfBusyIndicator.html) control.

```xml
<ContentPage   
    . . .
    xmlns:core="clr-namespace:Syncfusion.Maui.Core;assembly=Syncfusion.Maui.Core">

   <core:SfBusyIndicator x:Name="busyIndicator"
                          IsRunning = "True" />
</ContentPage>
```

```C#
using Syncfusion.Maui.Core;
. . .

public partial class MainPage : ContentPage
{
    public MainPage()
    {
        InitializeComponent();
        SfBusyIndicator busyIndicator = new SfBusyIndicator(){IsRunning = true};
        Content = busyIndicator;  
    }
}
```

## Setting AnimationType in .NET MAUI Busy Indicator

The [.NET MAUI Busy Indicator](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Core.SfBusyIndicator.html?tabs=tabid-1) provides some predefined animation types like Cupertino, LinearMaterial, and CircularMaterial. Users can select any one of the animation types using the [AnimationType](https://help.syncfusion.com/cr/maui/Syncfusion.Maui.Core.SfBusyIndicator.html#Syncfusion_Maui_Core_SfBusyIndicator_AnimationType) property.

```
       <ContentPage.Content>
        <core:SfBusyIndicator x:Name="busyIndicator"
                              IsRunning="True"
                              AnimationType="CircularMaterial" />
    </ContentPage.Content>

```

Run the application to render the following output:

![Getting started with .NET MAUI busy indicator](net-maui-busy-indicator-circular-material.gif)
