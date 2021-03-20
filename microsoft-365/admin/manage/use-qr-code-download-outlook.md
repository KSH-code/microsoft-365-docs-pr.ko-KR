---
title: QR 코드를 사용하여 Outlook 모바일 앱에 로그인
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: QR 코드를 사용하여 Outlook 모바일을 인증하고 다운로드하는 방법을 학습합니다.
ms.openlocfilehash: bc8ab14d3c1c0621e84d0c95ad7448c6c50825d6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914969"
---
# <a name="use-a-qr-code-to-sign-in-to-the-outlook-mobile-apps"></a><span data-ttu-id="1812d-103">QR 코드를 사용하여 Outlook 모바일 앱에 로그인</span><span class="sxs-lookup"><span data-stu-id="1812d-103">Use a QR code to sign-in to the Outlook mobile apps</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1812d-104">이 기능은 Microsoft 365 관리 센터에서 대상 지정 릴리스를 설정한 조직에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1812d-104">This feature is only available to organizations who have turned on Targeted Release in the Microsoft 365 admin center.</span></span> <span data-ttu-id="1812d-105">대상 지정 릴리스를 켜고 작동 방식에 대한 자세한 내용은 표준 또는 대상 지정 릴리스 옵션 설정 [을 참조하세요.](release-options-in-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="1812d-105">To turn on Targeted release and learn more about how it works, see [Set up the Standard or Targeted release options](release-options-in-office-365.md).</span></span> <span data-ttu-id="1812d-106">앞으로 몇 주 후에 공개 미리 보기를 통해 더 많은 조직으로 확장할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="1812d-106">We’ll be expanding to more organizations in the coming weeks through public preview.</span></span> <span data-ttu-id="1812d-107">공개 미리 보기를 사용하면 Microsoft 365 기능에 미리 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1812d-107">Public preview provides early access to Microsoft 365 features.</span></span>

<span data-ttu-id="1812d-108">Microsoft 365 관리자는 사용자 이름과 암호를 입력하지 않고도 모바일 장치에서 Android 또는 iOS용 Outlook 앱에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1812d-108">As the Microsoft 365 administrator, you can enable your users to sign in to Outlook for Android or iOS app on their mobile devices without having to enter their username and password.</span></span> <span data-ttu-id="1812d-109">QR 코드를 검사하면 사용자가 안전하게 인증하고 Outlook 모바일에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1812d-109">By scanning a QR code, users can securely authenticate and sign in to Outlook mobile.</span></span>

<span data-ttu-id="1812d-110">웹용 Outlook 또는 기타 데스크톱 Outlook 응용 프로그램에서는 사용자가 모바일 장치에서 Outlook을 사용할 수 있는 경우를 알리는 알림이 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1812d-110">In Outlook on the web or other desktop Outlook applications, users may see notifications informing them that they can use Outlook on their mobile device.</span></span> <span data-ttu-id="1812d-111">이러한 알림은 관리자가 Exchange Powershell을 사용하여 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1812d-111">These notifications can be managed by the administrator using Exchange Powershell.</span></span> <span data-ttu-id="1812d-112">사용자가 모바일 장치에서 앱을 다운로드하기 위해 SMS 문자 메시지를 보내면 컴퓨터에 QR 코드가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1812d-112">If users choose to send themselves an SMS text message to download the app on their mobile device, a QR code will appear on their computer.</span></span> <span data-ttu-id="1812d-113">QR 코드를 검사하여 휴대폰이나 태블릿에서 Outlook에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1812d-113">They will be able to scan the QR code to log into Outlook on their phone or tablet.</span></span> <span data-ttu-id="1812d-114">이 QR 코드는 한 번만 교환할 수 있는 짧은 라이브 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1812d-114">This QR code is a short lived token that can only be redeemed once.</span></span>

> [!NOTE]
> <span data-ttu-id="1812d-115">QR 코드를 생성하려면 사용자가 컴퓨터에서 다시 인증해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1812d-115">In some cases, your users will have to re-authenticate on their computer to generate the QR code.</span></span>

## <a name="use-exchange-powershell"></a><span data-ttu-id="1812d-116">Exchange PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="1812d-116">Use Exchange PowerShell</span></span>

<span data-ttu-id="1812d-117">이 기능은 기본적으로 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1812d-117">This feature is on by default.</span></span> <span data-ttu-id="1812d-118">이 기능을 사용하지 않도록 설정하기 위해 아래 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="1812d-118">To disable this feature, follow the steps below.</span></span>

1. <span data-ttu-id="1812d-119">[Exchange PowerShell에 연결합니다.](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps)</span><span class="sxs-lookup"><span data-stu-id="1812d-119">[Connect to Exchange PowerShell](/powershell/exchange/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>
2. <span data-ttu-id="1812d-120">PowerShell을 사용하여 사용자에게 Outlook 모바일 앱에 대해 알리는 알림을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1812d-120">Using PowerShell, you can disable the notifications informing your users about the Outlook mobile apps.</span></span> <span data-ttu-id="1812d-121">이렇게 하면 QR 코드 로그인 흐름이 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1812d-121">This will also prevent the QR code sign-in flow from being shown.</span></span>

```powershell
Set-OrganizationConfig -MobileAppEducationEnabled <Boolean>
```

<span data-ttu-id="1812d-122">관련 주제</span><span class="sxs-lookup"><span data-stu-id="1812d-122">Related topics</span></span>

[<span data-ttu-id="1812d-123">Set-OrganizationConfig</span><span class="sxs-lookup"><span data-stu-id="1812d-123">Set-OrganizationConfig</span></span>](/powershell/module/exchange/set-organizationconfig?view=exchange-ps)