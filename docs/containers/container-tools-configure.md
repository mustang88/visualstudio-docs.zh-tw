---
title: 設定 Visual Studio 容器工具
description: 設定 Visual Studio 中提供的工具，以使用 Docker 容器。
author: ghogen
ms.author: ghogen
ms.topic: how-to
ms.date: 03/20/2019
ms.technology: vs-azure
ms.openlocfilehash: d2b3e2821e7697ad53b10a7148c22140aa1a07af
ms.sourcegitcommit: 6cfffa72af599a9d667249caaaa411bb28ea69fd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/02/2020
ms.locfileid: "85283212"
---
# <a name="how-to-configure-visual-studio-container-tools"></a>如何設定 Visual Studio 容器工具

您可以使用 Visual Studio 設定來控制 Visual Studio 如何與 Docker 容器搭配運作的一些層面，包括使用 Docker 容器時，會影響效能和資源使用量的設定。

## <a name="container-tools-settings"></a>容器工具設定

從主功能表中，選擇 [工具] > [選項]****，並展開 [容器工具] > [設定]****。 容器工具設定隨即出現。

::: moniker range="vs-2017"

![Visual Studio 容器工具選項（顯示：自動在專案載入時提取所需的 Docker 映射）、自動在背景中啟動容器、自動在解決方案關閉時終止容器，而不提示信任 SSL 憑證。](./media/overview/visual-studio-docker-tools-options.png)
::: moniker-end

::: moniker range=">=vs-2019"

容器工具 **一般** 設定：

![Visual Studio 容器工具選項，顯示：視需要安裝 Docker Desktop，以及信任 ASP.NET Core SSL 憑證。](./media/configure-container-tools/tools-options-1.png)

容器工具 **單一專案** 和 **Docker Compose** 設定：

![Visual Studio 容器工具選項，顯示：在專案關閉時終止容器，在專案開啟時提取所需的 Docker 映射，並在專案開啟時執行容器。](./media/configure-container-tools/tools-options-2.png)
::: moniker-end

下表可協助您決定如何設定這些選項。

::: moniker range="vs-2017"
| Name | 預設值 | 套用至 | 描述 |
| -----|:---------------:|:----------:| ----------- |
| 自動在專案載入時提取所需的 Docker 映像 | 開啟 | Docker Compose | 為了提高載入專案時的效能，Visual Studio 會在背景中啟動 Docker 提取作業，因此當您準備好要執行程式碼時，映像已下載或正在下載中。 如果您只要載入專案並瀏覽程式碼，則可以關閉這項功能，避免下載您不需要的容器映像。 |
| 自動在背景中啟動容器 | 開啟 | Docker Compose | 同樣為了提高效能，Visual Studio 會在您建置並執行容器時建立一個容器，內含準備好可供使用的磁碟區裝載。 如果您想要控制何時建立容器，請關閉這項功能。 |
| 自動在解決方案關閉時終止容器 | 開啟 | Docker Compose | 如果您希望解決方案的容器在關閉解決方案或關閉 Visual Studio 之後繼續執行，請關閉這項功能。 |
| 不要提示信任 localhost SSL 憑證 | 關閉 | ASP.NET Core 2.1 專案 | 如果 localhost SSL 憑證不受信任，則除非核取此核取方塊，否則每次執行專案時 Visual Studio 都會提示。 |
::: moniker-end

::: moniker range=">=vs-2019"

下表說明 **一般** 設定：

| Name | 預設值 | 套用至 | 描述 |
| -----|:---------------:|:----------:| ----------- |
| 視需要安裝 Docker Desktop | 提示我 | 單一專案，Docker Compose | 選擇是否要在未安裝 Docker Desktop 時提示您。 |
| 信任 ASP.NET Core SSL 憑證 | 提示我 | ASP.NET Core 2.x 專案 | 當設定為 [ **提示我**] 時，如果 localhost SSL 憑證不受信任，Visual Studio 會在每次執行專案時提示。 |

下表描述 **單一專案** 和 **Docker Compose** 設定：

| Name | 預設值 | 套用至 | 描述 |
| -----|:---------------:|:----------:| ----------- |
| 在專案開啟時提取所需的 Docker 映射 | 是 | 單一專案，Docker Compose | 為了提高載入專案時的效能，Visual Studio 會在背景中啟動 Docker 提取作業，因此當您準備好要執行程式碼時，映像已下載或正在下載中。 如果您只是載入專案和流覽程式碼，您可以將設定為 **False** ，以避免下載不需要的容器映射。 |
| 在專案開啟時執行容器 | 是 | 單一專案，Docker Compose | 同樣地，為了提高效能，Visual Studio 會事先建立容器，以便在您建立和執行容器時可供使用。 如果您想要控制容器的建立時間，請將設定為 **False**。 |
| 在專案關閉時停止容器 | 是 | 單一專案和 Docker Compose | 如果您希望解決方案的容器在關閉解決方案或關閉 Visual Studio 之後繼續執行，請將設定為 **False** 。 |

::: moniker-end
> [!WARNING]
> 如果 localhost SSL 憑證不受信任，且您核取此方塊以抑制提示，則 HTTPS web 要求可能會在您的應用程式或服務中于執行時間失敗。 在此情況下，請取消核取 [不要提示]**** 核取方塊，執行您的專案，並在提示時表示信任。

## <a name="next-steps"></a>後續步驟

深入瞭解如何使用中的容器，請參閱本 [總覽](overview.md)的 Visual Studio。