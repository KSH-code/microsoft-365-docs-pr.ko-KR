---
title: S/MIME 설정 구성 - 웹에서 Outlook의 경우 Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Exchange Online에서 웹용 Outlook에서 S/MIME 설정을 보고 구성하기 위해 Exchange Online 관리자가 수행해야 하는 작업에 대한 간략한 설명입니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9acd7d4523754c1e07ece8fb0344d9f888c0ee3d
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825704"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a><span data-ttu-id="1425f-103">웹용 Outlook용 Exchange Online의 S/MIME 설정 구성</span><span class="sxs-lookup"><span data-stu-id="1425f-103">Configure S/MIME settings in Exchange Online for Outlook on the web</span></span>

<span data-ttu-id="1425f-104">Exchange Online 관리자는 웹용 Outlook(이전의 Outlook Web App)을 설정하여 S/MIME으로 보호되는 메시지 보내기와 받기를 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1425f-104">As an admin for Exchange Online, you can set up Outlook on the web (formerly known as Outlook Web App) to allow sending and receiving S/MIME-protected messages.</span></span> <span data-ttu-id="1425f-105">**Get-SmimeConfig 및** **Set-SmimeConfig** cmdlet을 사용하여 Exchange Online PowerShell에서 이 기능을 보고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="1425f-105">Use the **Get-SmimeConfig** and **Set-SmimeConfig** cmdlets to view and manage this feature in Exchange Online PowerShell.</span></span> <span data-ttu-id="1425f-106">Exchange Online PowerShell에 연결하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1425f-106">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

<span data-ttu-id="1425f-107">구문과 매개 변수에 대한 자세한 내용은 [Get-SmimeConfig 및](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) [Set-SmimeConfig를 참조하십시오.](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)</span><span class="sxs-lookup"><span data-stu-id="1425f-107">For detailed syntax and parameter information, see [Get-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) and [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a><span data-ttu-id="1425f-108">새로운 Microsoft Edge에 대한 고려 사항(Chromium 기반)</span><span class="sxs-lookup"><span data-stu-id="1425f-108">Considerations for new Microsoft Edge (Chromium-based)</span></span>

<span data-ttu-id="1425f-109">새로운 [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) 웹 브라우저에서 웹용 Outlook에서 S/MIME을 사용하려면 사용자(또는 다른 관리자)에서 Microsoft Edge 브라우저 확장명이 새 Microsoft Edge에 Microsoft S/MIME 확장명을 설치하도록 **ExtensionInstallForcelist라는** Microsoft Edge 브라우저 정책을 설정하고 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1425f-109">To use S/MIME in Outlook on the web in the new [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) web browser, you (or another admin) must set and configure the Microsoft Edge browser policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in the new Microsoft Edge.</span></span> <span data-ttu-id="1425f-110">정책 값은 다음과 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1425f-110">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="1425f-111">또한 이 정책을 적용하려면 도메인 가입 또는 Azure AD 가입 디바이스가 필요하므로 새 Microsoft Edge 브라우저에서 S/MIME을 사용하려면 도메인 가입 또는 Azure AD 가입 장치가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1425f-111">And note that applying this policy requires domain-joined or Azure AD-joined devices, so using S/MIME in the new Microsoft Edge browser effectively requires domain-joined or Azure AD-joined devices.</span></span>

<span data-ttu-id="1425f-112">**ExtensionInstallForcelist 정책에 대한 자세한** 내용은 [ExtensionInstallForcelist를 참조하십시오.](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)</span><span class="sxs-lookup"><span data-stu-id="1425f-112">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist).</span></span>

<span data-ttu-id="1425f-113">이 단계는 새 Microsoft Edge를 사용하기 위한 필수 조건입니다. 사용자가 설치한 S/MIME 컨트롤은 대체되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1425f-113">This step is a prerequisite for using new Microsoft Edge; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="1425f-114">사용자에게 S/MIME를 처음 사용하는 동안 Outlook에서 S/MIME 컨트롤을 다운로드하고 설치하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1425f-114">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="1425f-115">또는 사용자는 자동으로 웹용 Outlook 설정에서 **S/MIME으로** 이동하여 컨트롤의 다운로드 링크를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1425f-115">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="considerations-for-chrome"></a><span data-ttu-id="1425f-116">Chrome에 대한 고려 사항</span><span class="sxs-lookup"><span data-stu-id="1425f-116">Considerations for Chrome</span></span>

<span data-ttu-id="1425f-117">Google Chrome 웹 브라우저에서 웹용 Outlook에서 S/MIME을 사용하려면 사용자 또는 다른 관리자는 **ExtensionInstallForcelist라는** Chromium 정책을 설정하고 구성해야 Microsoft S/MIME 확장명이 Chrome에 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="1425f-117">To use S/MIME in Outlook on the web in the Google Chrome web browser, you (or another admin) must set and configure the Chromium policy named **ExtensionInstallForcelist** to install the Microsoft S/MIME extension in Chrome.</span></span> <span data-ttu-id="1425f-118">정책 값은 다음과 `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1425f-118">The policy value is `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`.</span></span> <span data-ttu-id="1425f-119">또한 이 정책을 적용하려면 도메인에 가입된 컴퓨터가 필요하므로 Chrome에서 S/MIME을 효과적으로 사용하려면 도메인에 가입된 컴퓨터가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1425f-119">And note that applying this policy requires domain-joined computers, so using S/MIME in Chrome effectively requires domain-joined computers.</span></span>

<span data-ttu-id="1425f-120">**ExtensionInstallForcelist 정책에 대한 자세한** 내용은 [ExtensionInstallForcelist를 참조하십시오.](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)</span><span class="sxs-lookup"><span data-stu-id="1425f-120">For details about the **ExtensionInstallForcelist** policy, see [ExtensionInstallForcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist).</span></span>

<span data-ttu-id="1425f-121">이 단계는 Chrome 사용에 대한 필수 구성 요소입니다. 사용자가 설치한 S/MIME 컨트롤은 대체되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1425f-121">This step is a prerequisite for using Chrome; it does not replace the S/MIME control that's installed by users.</span></span> <span data-ttu-id="1425f-122">사용자에게 S/MIME를 처음 사용하는 동안 Outlook에서 S/MIME 컨트롤을 다운로드하고 설치하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1425f-122">Users are prompted to download and install the S/MIME control in Outlook on the web during their first use of S/MIME.</span></span> <span data-ttu-id="1425f-123">또는 사용자는 자동으로 웹용 Outlook 설정에서 **S/MIME으로** 이동하여 컨트롤의 다운로드 링크를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1425f-123">Or, users can proactively go to **S/MIME** in their Outlook on the web settings to get the download link for the control.</span></span>

## <a name="for-more-information"></a><span data-ttu-id="1425f-124">자세한 내용</span><span class="sxs-lookup"><span data-stu-id="1425f-124">For more information</span></span>

[<span data-ttu-id="1425f-125">메시지 서명 및 암호화를 위한 S/MIME</span><span class="sxs-lookup"><span data-stu-id="1425f-125">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)
