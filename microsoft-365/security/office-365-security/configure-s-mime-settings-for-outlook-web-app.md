---
title: S/MIME 설정 구성 - 웹용 Outlook용 Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Exchange Online 관리자가 Exchange Online의 웹용 Outlook에서 S/MIME 설정을 보고 구성하기 위해 해야 하는 작업의 간략한 설명입니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a81db5ec933f1d0d6e2944103be53c0169dde62f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165682"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="af979-103">웹용 Outlook용 Exchange Online에서 S/MIME 설정 구성</span><span class="sxs-lookup"><span data-stu-id="af979-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="af979-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="af979-104">**Applies to**</span></span>
- [<span data-ttu-id="af979-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="af979-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="af979-106">Microsoft Defender for Office 365 요금제 1 및 계획 2</span><span class="sxs-lookup"><span data-stu-id="af979-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="af979-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="af979-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="af979-108">Exchange Online의 관리자는 S/MIME으로 보호된 메시지를 보내고 받을 수 있도록 웹용 Outlook(이전의 Outlook Web App)을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af979-108">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="af979-109">**Get-SmimeConfig** 및 **Set-SmimeConfig** cmdlet을 사용하여 Exchange Online PowerShell에서 이 기능을 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af979-109">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="af979-110">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af979-110">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="af979-111">구문과 매개 변수에 대한 자세한 내용은 [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) 및 [Set-SmimeConfig를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)</span><span class="sxs-lookup"><span data-stu-id="af979-111">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="af979-112">새로운 Microsoft Edge(Chromium 기반)에 대한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="af979-112">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="af979-113">새 [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) 웹 브라우저에서 웹용 Outlook에서 S/MIME을 사용하려면 사용자(또는 다른 관리자)가 **ExtensionInstallForcelist라는** Microsoft Edge 브라우저 정책을 설정하고 구성하여 새 Microsoft Edge에 Microsoft S/MIME 확장을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af979-113">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="af979-114">정책 값은 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="af979-114">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="af979-115">또한 이 정책을 적용하려면 도메인에 가입된 디바이스 또는 Azure AD 가입 장치가 필요하기 때문에 새 Microsoft Edge 브라우저에서 S/MIME를 효과적으로 사용하려면 도메인에 가입된 디바이스 또는 Azure AD 가입 장치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="af979-115">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="af979-116">**ExtensionInstallForcelist** 정책에 대한 자세한 내용은 [ExtensionInstallForcelist를 참조합니다.](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)</span><span class="sxs-lookup"><span data-stu-id="af979-116">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="af979-117">이 단계는 새 Microsoft Edge를 사용하기 위한 선행 단계입니다. 이 컨트롤은 사용자가 설치한 S/MIME 컨트롤을 대체하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af979-117">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="af979-118">S/MIME을 처음 사용하는 동안 웹용 Outlook에서 S/MIME 컨트롤을 다운로드하여 설치하라는 메시지가 사용자에게 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af979-118">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="af979-119">또는 사용자가 웹용 Outlook 설정에서 **S/MIME로** 사전 예방적으로 이동하여 컨트롤의 다운로드 링크를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af979-119">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="af979-120">Chrome에 대한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="af979-120">Considerations for Chrome</span></span>

<span data-ttu-id="af979-121">Google Chrome 웹 브라우저에서 웹용 Outlook에서 S/MIME을 사용하려면 사용자(또는 다른 관리자)가 Chrome에 Microsoft S/MIME 확장을 설치하도록 **ExtensionInstallForcelist라는** Chromium 정책을 설정하고 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="af979-121">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="af979-122">정책 값은 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` .</span><span class="sxs-lookup"><span data-stu-id="af979-122">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="af979-123">또한 이 정책을 적용하려면 도메인에 가입된 컴퓨터가 필요하기 때문에 Chrome에서 S/MIME을 효과적으로 사용하려면 도메인에 가입된 컴퓨터가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="af979-123">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="af979-124">**ExtensionInstallForcelist** 정책에 대한 자세한 내용은 [ExtensionInstallForcelist를 참조합니다.](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)</span><span class="sxs-lookup"><span data-stu-id="af979-124">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="af979-125">이 단계는 Chrome 사용을 위한 선행 단계입니다. 이 컨트롤은 사용자가 설치한 S/MIME 컨트롤을 대체하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="af979-125">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="af979-126">S/MIME을 처음 사용하는 동안 웹용 Outlook에서 S/MIME 컨트롤을 다운로드하여 설치하라는 메시지가 사용자에게 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af979-126">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="af979-127">또는 사용자가 웹용 Outlook 설정에서 **S/MIME로** 사전 예방적으로 이동하여 컨트롤의 다운로드 링크를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af979-127">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="af979-128">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="af979-128">For more information</span></span>

[<span data-ttu-id="af979-129">메시지 서명 및 암호화를 위한 S/MIME</span><span class="sxs-lookup"><span data-stu-id="af979-129">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
