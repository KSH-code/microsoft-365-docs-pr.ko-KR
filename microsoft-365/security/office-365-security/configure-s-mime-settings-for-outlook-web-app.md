---
title: S/MIME 설정 구성-웹에서 Outlook 용 Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Exchange Online 관리자가 웹에서 Outlook의 S/MIME 설정을 보고 구성 하기 위해 수행 해야 하는 작업에 대 한 간략 한 설명입니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2c1496025124717688cc812e22e0d8fe3a441112
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616625"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="d04cd-103">웹용 Outlook에 대 한 Exchange Online의 S/MIME 설정 구성</span><span class="sxs-lookup"><span data-stu-id="d04cd-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

<span data-ttu-id="d04cd-104">Exchange Online 관리자는 웹에서 Outlook (이전의 Outlook Web App)을 설정 하 여 S/MIME로 보호 된 메시지를 보내고 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d04cd-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="d04cd-105">**Get-smimeconfig** 및 **get-smimeconfig** cmdlet을 사용 하 여 Exchange Online PowerShell에서이 기능을 보고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d04cd-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="d04cd-106">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d04cd-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="d04cd-107">구문과 매개 변수에 대 한 자세한 내용은 [get-smimeconfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) 및 [get-smimeconfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d04cd-107">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="d04cd-108">새 Microsoft Edge에 대 한 고려 사항 (Chromium 기반)</span><span class="sxs-lookup"><span data-stu-id="d04cd-108">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="d04cd-109">새 [Microsoft edge](https://www.microsoft.com/windows/microsoft-edge) 웹 브라우저에서 웹의 Outlook에서 S/mime을 사용 하려면 사용자 (또는 다른 관리자)가 새 microsoft Edge에 microsoft S/MIME 확장명을 설치 하도록 **Extensioninstallforcelist** 라는 microsoft edge 브라우저 정책을 설정 하 고 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d04cd-109">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in new Microsoft Edge.</span></span> <span data-ttu-id="d04cd-110">정책 값은 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d04cd-110">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="d04cd-111">또한이 정책을 적용 하려면 도메인에 가입 된 컴퓨터가 필요 하므로 새 Microsoft Edge 브라우저에서 S/MIME을 사용 하려면 도메인에 가입한 컴퓨터가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d04cd-111">And note that applying this policy requires domain-joined computers, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined computers.</span></span>

<span data-ttu-id="d04cd-112">**Extensioninstallforcelist** 정책에 대 한 자세한 내용은 [extensioninstallforcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d04cd-112">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="d04cd-113">이 단계는 새 Microsoft Edge를 사용 하기 위한 필수 구성 요소입니다. 사용자가 설치한 S/MIME 컨트롤은 대체 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d04cd-113">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="d04cd-114">S/MIME을 처음 사용할 때 Outlook에서 S/MIME 컨트롤을 다운로드 하 고 설치 하 라는 메시지가 사용자에 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d04cd-114">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="d04cd-115">또는 사용자가 웹 설정에 따라 Outlook에서 **S/MIME** 로 바로 이동 하 여 컨트롤의 다운로드 링크를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d04cd-115">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="d04cd-116">Chrome에 대 한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="d04cd-116">Considerations for Chrome</span></span>

<span data-ttu-id="d04cd-117">Google Chrome 웹 브라우저에서 웹의 Outlook에서 S/MIME을 사용 하려면 사용자 (또는 다른 관리자)가 Chromium 정책을 **설정 하 고** 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d04cd-117">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="d04cd-118">정책 값은 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 입니다.</span><span class="sxs-lookup"><span data-stu-id="d04cd-118">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="d04cd-119">또한이 정책을 적용 하려면 도메인에 가입 된 컴퓨터가 필요 하므로 Chrome에서 S/MIME을 사용 하려면 도메인에 가입 된 컴퓨터가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d04cd-119">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="d04cd-120">**Extensioninstallforcelist** 정책에 대 한 자세한 내용은 [extensioninstallforcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="d04cd-120">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="d04cd-121">이 단계는 Chrome을 사용 하기 위한 필수 구성 요소입니다. 사용자가 설치한 S/MIME 컨트롤은 대체 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d04cd-121">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="d04cd-122">S/MIME을 처음 사용할 때 Outlook에서 S/MIME 컨트롤을 다운로드 하 고 설치 하 라는 메시지가 사용자에 게 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d04cd-122">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="d04cd-123">또는 사용자가 웹 설정에 따라 Outlook에서 **S/MIME** 로 바로 이동 하 여 컨트롤의 다운로드 링크를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d04cd-123">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="d04cd-124">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="d04cd-124">For more information</span></span>

[<span data-ttu-id="d04cd-125">메시지 서명 및 암호화를 위한 S/MIME</span><span class="sxs-lookup"><span data-stu-id="d04cd-125">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
