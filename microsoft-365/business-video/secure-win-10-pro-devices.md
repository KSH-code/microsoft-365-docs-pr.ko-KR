---
title: Microsoft 365 Business Premium을 사용하여 Windows 10 Pro 장치 정책 관리
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 Business Premium을 사용하여 Windows 10 Pro 장치 정책을 관리하는 방법에 대해 자세히 알아보습니다.
ms.openlocfilehash: f42c175543ae16ae645c17997b20ed67aa5d705c
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926009"
---
# <a name="manage-windows-10-pro-device-policies"></a><span data-ttu-id="1c9e0-103">Windows 10 Pro 장치 정책 관리</span><span class="sxs-lookup"><span data-stu-id="1c9e0-103">Manage Windows 10 Pro device policies</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSL?autoplay=false]

<span data-ttu-id="1c9e0-104">Microsoft 365 Business를 사용하여 Windows 10 장치에서 Windows Defender 바이러스 백신이 활성화되고 Microsoft 업데이트가 사용자의 장치에 자동으로 다운로드되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c9e0-104">You can use Microsoft 365 Business to ensure that Windows Defender Antivirus is activated on Windows 10 devices and Microsoft updates are automatically downloaded to users' devices.</span></span>

## <a name="try-it"></a><span data-ttu-id="1c9e0-105">사용해 보세요!</span><span class="sxs-lookup"><span data-stu-id="1c9e0-105">Try it!</span></span>

1. <span data-ttu-id="1c9e0-106">Microsoft 365 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9e0-106">Sign in to the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="1c9e0-107">**정책에서** 정책 추가를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9e0-107">Under **Policies**, choose Add policy.</span></span>
1. <span data-ttu-id="1c9e0-108">정책 추가 **창에서** 정책 이름 아래에 이름을 입력한 다음 정책 유형에서 **Windows 10** 장치 **구성을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1c9e0-108">In the **Add policy** pane, enter a name under **Policy name**, and then select **Windows 10 Device Configuration** under **Policy type**.</span></span>
1. <span data-ttu-id="1c9e0-109">하위 **설정을 표시하려면 Windows 10** 디바이스 보안 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9e0-109">Choose **Secure Windows 10 devices** to see the sub-settings.</span></span>
1. <span data-ttu-id="1c9e0-110">바이러스 백신을 **사용하여** 바이러스 및 기타 위협으로부터 PC를 보호하는 Windows Defender Windows **10** 장치를 최신 상태로 유지하는 것이 자동으로 켜져 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c9e0-110">Make sure that **Help protect PCs from viruses and other threats using Windows Defender Antivirus** and **Keep Windows 10 devices up to date automatically** are turned on.</span></span>
1. <span data-ttu-id="1c9e0-111">이러한 설정을 사용할 사용자 **아래에는** 모든 사용자가 기본적으로 선택되지만, 변경을 선택하여 만든 보안 그룹을 선택할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="1c9e0-111">Under **Who will get these settings?**, all users are selected by default, but you can choose **Change** to select any security groups you've created.</span></span>
1. <span data-ttu-id="1c9e0-112">정책 만들기를 완료하고 추가를 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="1c9e0-112">To finish creating the policy, choose **Add**.</span></span>
1. <span data-ttu-id="1c9e0-113">정책 추가 **페이지에서** 닫기 를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1c9e0-113">On the **Add policy** page, choose **Close**.</span></span>
1. <span data-ttu-id="1c9e0-114">관리 센터 홈 페이지에서 정책을 선택하고 정책 페이지에서  정책을 검토하여 새 정책이 추가된 것을 **확인하십시오.**</span><span class="sxs-lookup"><span data-stu-id="1c9e0-114">On the admin center home page, confirm that your new policy was added by choosing **Policies** and reviewing your policy on the **Policies** page.</span></span>
1. <span data-ttu-id="1c9e0-115">정책이 적용된지 확인하려면 사용자의 Windows 10 장치에서 Windows 업데이트로 이동하여 고급 옵션을 선택하고 설정이 회색으로 표시되어 있는지 확인합니다. </span><span class="sxs-lookup"><span data-stu-id="1c9e0-115">To verify that the policy has taken effect, on a user's Windows 10 device, go to Windows Update, choose **Advanced options**, and confirm that settings are grayed out.</span></span>

    <span data-ttu-id="1c9e0-116">그런 다음 **업데이트** 배달 방법 선택을 클릭하고 설정이 회색으로 표시되고 다음 메시지가 나타나는지 확인합니다. 일부 설정은 조직에서 숨기거나 **관리합니다.**</span><span class="sxs-lookup"><span data-stu-id="1c9e0-116">Then, click **Choose how updates are delivered**, and confirm that settings are grayed out and the following message appears: **Some settings are hidden or managed by your organization**.</span></span>

