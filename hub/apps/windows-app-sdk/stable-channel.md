---
title: Stable channel release notes for the Windows App SDK 
description: Provides information about the stable release channel for the Windows App SDK.
ms.topic: article
ms.date: 05/21/2021
keywords: windows win32, windows app development, Windows App SDK 
ms.author: zafaraj
author: zaryaf
ms.localizationpriority: medium
---

# Stable channel release notes for the Windows App SDK

The stable channel provides releases of the Windows App SDK that are supported for use by apps in production environments. Apps that use the stable release of the Windows App SDK can also be published to the Microsoft Store.

The following releases of the stable channel are currently available:

- [Version 0.8](#version-08)
- [Version 0.5](#version-05)

If you'd like to upgrade an existing app from an older version of the Windows App SDK to a newer version, see [Update existing projects to the latest release of the Windows App SDK](update-existing-projects-to-the-latest-release.md). 

> [!NOTE]
> The Windows App SDK was previously known by the code name **Project Reunion**. Some SDK assets such as the VSIX extension and NuGet packages still use the code name, but these assets will be renamed in a future release. Some areas of the documentation still use **Project Reunion** when referring to an existing asset or a specified earlier release.

## Version 0.8

The latest available release of the stable channel is the servicing release 0.8.2.

> [!div class="button"]
> [Download](https://aka.ms/projectreunion/vsixdownload)

### Version 0.8.5

This is a servicing release of the Windows App SDK that includes more critical bug fixes for the 0.8.0 release. 

#### Bug fixes

- Fixed issue that was causing WinUI apps using [pointer input](/windows/winui/api/microsoft.ui.xaml.input.pointer) to crash. 
- Fixed issue causing the title bar buttons (min, max, close) to not have rounded corners on Windows 11. 
- Fixed issue causing the resizing layout options to not appear when hovering over maximize/restore button on Windows 11. 
- Fixed issue causing a crashing exception where creating a [PointCollection](/windows/winui/api/microsoft.ui.xaml.media.pointcollection) object. For more information, see [issue 971](https://github.com/microsoft/CsWinRT/issues/971) on Github. 

The limitations and known issues for version 0.8 also apply to version 0.8.5, unless marked otherwise in the [section below](#limitations).

### Version 0.8.4

This is a servicing release of the Windows App SDK that includes more critical bug fixes for the 0.8.0 release. 

#### Bug fixes

- Fixes for custom title bars so that [ContentDialog](/windows/winui/api/microsoft.ui.xaml.controls.contentdialog) doesn't cover it up, and the title bar buttons are rounded.
- Fix for a crash in image processing when the display scale is changed.
- Fixes clipping bugs where UI disappear or clipped incorrectly

The limitations and known issues for version 0.8 also apply to version 0.8.4, unless marked otherwise in the [section below](#limitations).

### Version 0.8.3

This is a servicing release of the Windows App SDK that includes more critical bug fixes for the 0.8.0 release. 

#### Bug fixes

Keyboard focus was being lost when a window was minimized and then restored, requiring a mouse click to restore focus.

The limitations and known issues for version 0.8 also apply to version 0.8.3, unless marked otherwise in the [section below](#limitations).

### Version 0.8.2

This is a servicing release of the Windows App SDK that includes more critical bug fixes for the 0.8.0 release. 

#### Bug fixes

- Windows App SDK and WinUI 3 are now supported in Visual Studio 2022 Preview 2 and above.
- For .NET apps, you may receive the following error when passing in an array of enums: `Object contains non-primitive or non-blittable data.`
- Writing using the HandWriting Panel inside a textbox causes a crash
- Icons/images always load at their 100% scale value rather than based on the monitor scale value
- Garbage collection of **EventSource\<T\>** causes subsequent failure to unsubscribe handlers (see [GitHub issue](https://github.com/microsoft/CsWinRT/issues/842) for more details)
- Security fix – see [CVE-2021-34533](https://msrc.microsoft.com/update-guide/en-US/vulnerability/CVE-2021-34533) for more details.
- [SwapChainPanel.CompositionScaleChanged](/windows/winui/api/microsoft.ui.xaml.controls.swapchainpanel.compositionscalechanged) sometimes returning incorrect CompositionScale values after changing display scale

The limitations and known issues for version 0.8 also apply to version 0.8.2, unless marked otherwise in the [section below](#limitations).

### Version 0.8.1

This is a servicing release of the Windows App SDK that includes a few critical bug fixes for the 0.8.0 release. 

#### Bug fixes

- Windows App SDK cannot run on the latest Windows Insider build
- Crash in EditableComboBox when entering a value that does not appear in dropdown
- WebView2 doesn't allow user to tab out once focused has been received
- Fully qualify Windows.Foundation.Metadata.DefaultOverload namespace in WinUI generated code to avoid namespace ambiguity 
    - This fixes bug [#5108](https://github.com/microsoft/microsoft-ui-xaml/issues/5108).
- Security fix – see [CVE-2021-34489](https://msrc.microsoft.com/update-guide/en-US/vulnerability/CVE-2021-34489) for more details.

The limitations and known issues for version 0.8 also apply to version 0.8.1, unless marked otherwise in the [section below](#limitations).

### Version 0.8.0

#### New features and updates

This release supports all [stable channel features](release-channels.md#features-available-by-release-channel).

**WinUI 3**

This release includes many bug fixes and improved stabilization across WinUI 3. These are all of the new changes in WinUI 3 since the release of WinUI 3 - Project Reunion 0.5:

- The Pivot control has been added back in and can now be used in any WinUI 3 app.
- All bug fixes from Project Reunion v0.5.5, v0.5.6, and v0.5.7 are included with this release.
- New bug fixes, including:
    - Mouse right-click in TextBox crashes the application
    - NavigationView causes crash in UWP, Reunion 0.5 Preview
    - ProgressBar doesn't show difference between Paused and Error option
    - Crash in RichEditBox when copying/pasting/changing text style
    - Window caption buttons are misplaced when SetTitleBar is not set or null

    **For the full list of bugs addressed in this release, see [our GitHub repo](https://aka.ms/winui3/0.8/bugs-fixed).** 

- The `ColorHelper.ToDisplayName` API is no longer available. 
- The following types have been removed:
    - `Microsoft.Graphics.IGeometrySource2D`
    - `Microsoft.Graphics.IGeometrySource2DInterop`

    Use `Windows.Graphics.IGeometrySource2D` and `Windows.Graphics.IGeometrySource2DInterop` instead.

- All types in the `Microsoft.System` namespace have been moved to the `Microsoft.UI.Dispatching` namespace, including the [DispatcherQueue class](/windows/winui/api/microsoft.system/dispatcherqueue.md).

- The `AcrylicBrush.BackgroundSource` property has been removed, since `HostBackdrop` is not supported as a `BackgroundSource` in WinUI 3.

For more information on WinUI, see [Windows UI 3 Library (WinUI)](../winui/index.md).

To see WinUI 3 controls and features in action, you can clone and build the WinUI 3 Controls Gallery app [from GitHub](https://github.com/microsoft/Xaml-Controls-Gallery/tree/winui3), or download the app [from the Microsoft Store](https://www.microsoft.com/p/winui-3-controls-gallery/9p3jfpwwdzrc).

To get started developing with WinUI, check out the following articles:
- [WinUI 3 project templates in Visual Studio](../winui/winui3/winui-project-templates-in-visual-studio.md)
- [Get started developing apps with WinUI 3](../winui/winui3/get-started-winui3-for-desktop.md)
- [WinUI 3 desktop apps and basic Win32 interop](../winui/winui3/desktop-winui3-app-with-basic-interop.md)
- [WinUI 3 API Reference](/windows/winui/api)

**DWriteCore**

This release of DWriteCore includes the following new and updated features. DWriteCore is introduced and described in the [DWriteCore overview](/windows/win32/directwrite/dwritecore-overview).

- DWriteCore now has support for underline&mdash;see [**IDWriteTextLayout::GetUnderline**](/windows/win32/api/dwrite/nf-dwrite-idwritetextlayout-getunderline) and [**IDWriteTextLayout::SetUnderline**](/windows/win32/api/dwrite/nf-dwrite-idwritetextlayout-setunderline).
- Support for strikethrough&mdash;see [**IDWriteTextLayout::GetStrikethrough**](/windows/win32/api/dwrite/nf-dwrite-idwritetextlayout-getstrikethrough) and [**IDWriteTextLayout::SetStrikethrough**](/windows/win32/api/dwrite/nf-dwrite-idwritetextlayout-setstrikethrough).
- Support for vertical text via [**IDWriteTextLayout**](/windows/win32/api/dwrite/nn-dwrite-idwritetextlayout)&mdash;see [Vertical text](/windows/win32/directwrite/vertical-text).
- All of the methods of the [**IDWriteTextAnalyzer**](/windows/win32/api/dwrite/nn-dwrite-idwritetextanalyzer) and [**IDWriteTextAnalyzer1**](/windows/win32/api/dwrite_1/nn-dwrite_1-idwritetextanalyzer1) interfaces are implemented.
- The [**DWriteCoreCreateFactory**](/windows/windows-app-sdk/api/win32/dwrite_core/nf-dwrite_core-dwritecorecreatefactory) free function creates a factory object that is used for subsequent creation of individual DWriteCore objects.

> [!NOTE]
> [**DWriteCoreCreateFactory**](/windows/windows-app-sdk/api/win32/dwrite_core/nf-dwrite_core-dwritecorecreatefactory) is functionally the same as the [**DWriteCreateFactory**](/windows/win32/api/dwrite/nf-dwrite-dwritecreatefactory) function exported by the system version of DirectWrite. The DWriteCore function has a different name to avoid ambiguity in the event that you link both `DWriteCore.lib` and `DWrite.lib`.

For DWriteCore and DirectWrite API reference, see [DWriteCore API Reference](/windows/windows-app-sdk/api/win32/_dwritecore/) and [DirectWrite API Reference](/windows/win32/directwrite/reference).

**MRTCore**

- The **Build Action** for resources is automatically set when you add the resource to your project, reducing the need for manual project configuration.

#### Limitations

- This release is not currently supported on the Dev Channel of the [Windows Insider Program](https://insider.windows.com). **This is fixed in version 0.8.1**.

- Desktop apps (C# .NET 5 or C++ desktop): This release is supported for use only in desktop apps (C++ or C# with .NET 5) that are packaged using MSIX. To use the Windows App SDK in unpackaged desktop apps, you must use the [experimental release channel](experimental-channel.md).

- UWP apps: This release is not supported for UWP apps that are used in production environments. To use the Windows App SDK in UWP apps, you must use the [experimental release channel](experimental-channel.md).

#### Known issues 

- WinUI 3 tooling such as Live Visual Tree, Live Property Explorer, and Hot Reload in version 0.8 and later requires Visual Studio 2019 16.11 Preview 3 or later.

- Apps currently using WinUI 3 and the Windows App SDK 0.8 cannot use class libraries that use Project Reunion 0.5. Update the class libraries to use the Windows App SDK 0.8.

- .NET apps must target build 18362 or higher: Your TFM must be set to net5.0-windows10.0.18362 or higher, and your packaging project's must be set to 18362 or higher. For more info, see [GitHub issue #921](https://github.com/microsoft/WindowsAppSDK/issues/921).

- You may encounter a crash when switching frequently between light and dark mode.

- For .NET apps, you may receive the following error when passing in an array of enums: `Object contains non-primitive or non-blittable data.` **This is fixed in version 0.8.2**.
	
- For .NET apps, there is currently no way  to opt out of an image getting indexed as an app resource using the Visual Studio UI. To work around this, add a Directory.Build.targets (see [Customize your build - Visual Studio](/visualstudio/msbuild/customize-your-build) for instructions) to the project and remove the image(s) as follows:
 
    - To remove specific images (note that the relative path is needed):
        ```xml
        <Project> 
        <ItemGroup> 
            <Content Remove="..\Bitmap1.bmp" />
        </ItemGroup>
        </Project>
        ```
 
    - To remove images based on metadata: 
        ```xml
        <Project>
        <ItemGroup>
            <Content Remove="@(None->WithMetadataValue('Pack','true'))" />
        </ItemGroup>
        </Project>
        ```

    A fix for this issue is planned for an upcoming release - at that point, the above workarounds will no longer be needed.

## Version 0.5

The latest available servicing release is [0.5.7](https://github.com/microsoft/WindowsAppSDK/discussions/820).

> [!div class="button"]
> [Download](https://aka.ms/projectreunion/vsixdownload)

### New features and updates

This release supports all [stable channel features](release-channels.md#features-available-by-release-channel).

### Known issues and limitations

This release has the following limitations and known issues:

- **Desktop apps (C# .NET 5 or C++ desktop)**: This release is supported for use only in desktop apps (C++ or C# with .NET 5) that are packaged using MSIX. To use the Windows App SDK in unpackaged desktop apps, you must use the [experimental release channel](experimental-channel.md).
- **UWP apps**: This release is not supported for UWP apps that are used in production environments. To use the Windows App SDK in UWP apps, you must use a release from the [experimental release channel](experimental-channel.md).
- **.NET apps must target build 18362 or higher**: Your TFM must be set to `net5.0-windows10.0.18362` or higher, and your packaging project's `<TargetPlatformVersion>` must be set to 18362 or higher. For more info, see the [known issue on GitHub](https://github.com/microsoft/WindowsAppSDK/issues/921).

## Related topics

- [Preview channel](preview-channel.md)
- [Experimental channel](experimental-channel.md)
- [Set up your development environment](set-up-your-development-environment.md)
- [Create a new project that uses the Windows App SDK](../winui/winui3/create-your-first-winui3-app.md)
- [Use the Windows App SDK in an existing project](use-windows-app-sdk-in-existing-project.md)
- [Deploy apps that use the Windows App SDK](../package-and-deploy/index.md#apps-that-use-the-windows-app-sdk)
