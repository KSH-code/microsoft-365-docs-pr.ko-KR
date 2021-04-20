---
title: 장치 제거
description: Microsoft Managed Desktop 관리에서 장치 제거
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: fa1cb7307fddd815a2a9249c5a98739d21bd2418
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893812"
---
# <a name="remove-devices"></a><span data-ttu-id="b68bd-103">장치 제거</span><span class="sxs-lookup"><span data-stu-id="b68bd-103">Remove devices</span></span>

<span data-ttu-id="b68bd-104">관리 포털을 사용하여 Microsoft Managed Desktop 관리에서 장치를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b68bd-104">You can remove devices from Microsoft Managed Desktop management by using the Admin portal.</span></span> <span data-ttu-id="b68bd-105">이 작업은 영구적이지만 등록 단계에 따라 Microsoft Managed Desktop에 다시 등록할 [수 있습니다.](../get-started/register-devices-self.md)</span><span class="sxs-lookup"><span data-stu-id="b68bd-105">This action is permanent, but you can register them with Microsoft Managed Desktop again by following the [registration steps](../get-started/register-devices-self.md).</span></span>

<span data-ttu-id="b68bd-106">장치를 제거하면 다음과 같은 모든 문제가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b68bd-106">When you remove a device, all of the following occur:</span></span>

- <span data-ttu-id="b68bd-107">Autopilot에서 장치를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b68bd-107">We remove the device from Autopilot.</span></span>
- <span data-ttu-id="b68bd-108">모든 "최신 작업 공간" 장치 그룹에서 장치를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b68bd-108">We remove the device from  all "Modern Workplace" device groups.</span></span>
- <span data-ttu-id="b68bd-109">관리 포털의 **장치** 블레이드에서 장치를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b68bd-109">We remove the device from the **Devices** blade in the Admin portal.</span></span>

<span data-ttu-id="b68bd-110">장치를 제거할 때 Azure AD(Azure Active Directory) 및 Microsoft Intune에서도 장치를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b68bd-110">When you remove a device, you have the option to also remove it from Azure Active Directory (Azure AD) and Microsoft Intune.</span></span>
 
> [!CAUTION]
> <span data-ttu-id="b68bd-111">Azure AD 및 Microsoft Intune에서 장치와 관련된 개체가 영구적으로 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="b68bd-111">Removing the objects related to a device from Azure AD and Microsoft Intune is permanent.</span></span> <span data-ttu-id="b68bd-112">개체를 제거하면 Intune 및 Azure Portal에서 디바이스를 보거나 관리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b68bd-112">If you remove the objects, you won't be able to view or manage the devices from the Intune and Azure portals.</span></span> <span data-ttu-id="b68bd-113">장치는 회사의 회사 리소스에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b68bd-113">The devices won't be able to access their company's corporate resources.</span></span> <span data-ttu-id="b68bd-114">장치가 삭제된 후 로그인을 시도하면 회사 데이터가 삭제될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b68bd-114">Company data might be deleted from them if the devices try to sign in after they're deleted.</span></span>

1. <span data-ttu-id="b68bd-115">[Microsoft 끝점 관리자의](https://endpoint.microsoft.com/) **왼쪽** 탐색 창에서 장치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b68bd-115">In [Microsoft Endpoint Manager](https://endpoint.microsoft.com/), select **Devices** in the left navigation pane.</span></span>
2. <span data-ttu-id="b68bd-116">메뉴의 **Microsoft Managed Desktop** 섹션을 찾아 장치를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b68bd-116">Look for the **Microsoft Managed Desktop** section of the menu and select **Devices**.</span></span>
3. <span data-ttu-id="b68bd-117">Microsoft Managed Desktop Devices 작업 영역에서 삭제할 장치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b68bd-117">In the Microsoft Managed Desktop Devices workspace, select the devices you want to delete.</span></span>
4. <span data-ttu-id="b68bd-118">장치 **작업을 선택한** 다음 **플라이** 인을 여는 장치 삭제를 선택하여 장치를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="b68bd-118">Select **Device actions**, and then select **Delete Device** which opens a fly-in to remove the devices.</span></span>
5. <span data-ttu-id="b68bd-119">플라이 인에서 선택한 장치를 검토한 다음 장치 **제거를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b68bd-119">In the fly-in, review the selected devices and then select **Remove devices**.</span></span> <span data-ttu-id="b68bd-120">Azure AD 및 Intune 개체도 동시에 제거하려면 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b68bd-120">If you want to also remove the Azure AD and Intune objects at the same time, select the check box.</span></span> <span data-ttu-id="b68bd-121">장치 제거를 완료하는 데 몇 분 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b68bd-121">Device removal can take a few minutes to complete.</span></span>

> [!NOTE]
> <span data-ttu-id="b68bd-122">보류 중인 등록 상태인 디바이스는 **제거할 수** 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b68bd-122">You can't remove devices that are in a **pending** registration state.</span></span>