---
description: Learn about how to package and deploy Windows apps.
title: Package and deploy
ms.topic: article
ms.date: 06/17/2021
ms.localizationpriority: medium
ms.author: mcleans
author: mcleanbyron
---

# Package and deploy

For guidance about packaging and deploying different types of Windows apps, see the following articles. Generally we recommend using [MSIX](/windows/msix) for a modern and reliable deployment experience for your customers. However, you can also deploy your apps using other installation technologies.

## Apps that use the Windows App SDK

Before configuring your apps for deployment, review [the Windows App SDK runtime architecture](../windows-app-sdk/deployment-architecture.md) to learn more about the dependencies your app takes when it uses the Windows App SDK.

### Packaged apps

If you build an app that uses the [Windows App SDK](../windows-app-sdk/index.md) (either a [WinUI 3 app](../get-started/index.md#app-types) or a different type of app that [uses the Windows App SDK NuGet package](../windows-app-sdk/use-windows-app-sdk-in-existing-project.md)), you can package and deploy your app using MSIX.

For instructions on how to deploy the Windows App SDK runtime with your packaged app, see these articles:

- [Windows App SDK deployment guide for packaged apps](../windows-app-sdk/deploy-packaged-apps.md)
- [Manage your MSIX deployment](/windows/msix/desktop/managing-your-msix-deployment-overview)

### Unpackaged apps

For instructions on how to deploy the Windows App SDK runtime with your unpackaged app, see these articles:

- [Windows App SDK deployment guide for unpackaged apps](../windows-app-sdk/deploy-unpackaged-apps.md)
- [Tutorial: Build and deploy an unpackaged app that uses the Windows App SDK](../windows-app-sdk/tutorial-unpackaged-deployment.md)

## Win32 and .NET desktop apps

If you build a Win32 desktop app (also sometimes called a *classic desktop app*) or a .NET app (including WPF and Windows Forms), you can package and deploy your app using MSIX.

- [Create an MSIX package from an existing installer](/windows/msix/packaging-tool/create-an-msix-overview)
- [Build an MSIX package from source code](/windows/msix/desktop/source-code-overview)
- [Manage your MSIX deployment](/windows/msix/desktop/managing-your-msix-deployment-overview)

You can also package and deploy these types of apps using other installation technologies.

- [Application installation and servicing](/windows/desktop/application-installing-and-servicing)
- [Windows Installer](/windows/desktop/msi/windows-installer-portal)
- [.NET application publishing overview](/dotnet/core/deploying/)
- [Deploying the .NET Framework and applications](/dotnet/framework/deployment/)
- [Deploying a WPF application](/dotnet/framework/wpf/app-development/deploying-a-wpf-application-wpf)
- [ClickOnce Deployment for Windows Forms](/dotnet/framework/winforms/clickonce-deployment-for-windows-forms)

## UWP apps

UWP apps are packaged and deployed using MSIX.

- [Overview of packaging UWP apps](/windows/uwp/packaging)
- [Package a UWP app in Visual Studio](/windows/msix/package/packaging-uwp-apps)
- [Manage your MSIX deployment](/windows/msix/desktop/managing-your-msix-deployment-overview)

## Related topics

- [Set up your development environment](../windows-app-sdk/set-up-your-development-environment.md)
- [Get started developing apps](../get-started/index.md)
