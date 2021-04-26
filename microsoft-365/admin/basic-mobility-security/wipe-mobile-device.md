---
title: 기본 모바일 및 보안에서 모바일 장치 지우기
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
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: 기본 제공 기본 이동성 및 보안을 사용하여 등록된 장치에서 정보를 제거합니다.
ms.openlocfilehash: 7830a0f4ef609f6465c171ecab2c9e3c48198424
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023860"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="5d3ff-103">기본 모바일 및 보안에서 모바일 장치 지우기</span><span class="sxs-lookup"><span data-stu-id="5d3ff-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="5d3ff-104">Microsoft 365의 기본 제공 Basic Mobility and Security를 사용하여 조직 정보만 제거하거나 초기화하여 모바일 장치에서 모든 정보를 삭제하고 공장 설정으로 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5d3ff-105">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="5d3ff-105">Before you begin</span></span>

<span data-ttu-id="5d3ff-106">모바일 장치는 중요한 조직 정보를 저장하고 조직의 Microsoft 365 리소스에 대한 액세스를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="5d3ff-107">조직의 정보를 보호하기 위해 공장 초기화 또는 회사 데이터 제거를 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>

- <span data-ttu-id="5d3ff-108">**초기화:** 설치된 응용 프로그램, 사진 및 개인 정보를 포함하여 사용자의 모바일 장치에서 모든 데이터를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="5d3ff-109">초기화가 완료되면 장치가 공장 설정으로 복원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-109">When the wipe is complete, the device is restored to its factory settings.</span></span>

- <span data-ttu-id="5d3ff-110">**회사 데이터 제거:** 조직 데이터만 제거하고 사용자의 모바일 장치에 설치된 응용 프로그램, 사진 및 개인 정보를 그대로 떠날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>

- <span data-ttu-id="5d3ff-111">**장치가 초기화되면(회사** 데이터 초기화 또는 제거) 관리되는 장치 목록에서 장치가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="5d3ff-112">**장치** 자동 초기화: 사용자가 장치 암호를 특정 횟수로 입력하지 못하면 장치를 자동으로 초기화하는 기본 이동성 및 보안 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="5d3ff-113">이렇게하려면 [Create device security policies in basic mobility and security의 단계를 수행합니다.](create-device-security-policies.md)</span><span class="sxs-lookup"><span data-stu-id="5d3ff-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies.md).</span></span>
    
- <span data-ttu-id="5d3ff-114">**장치를 초기화할** 때 사용자 환경을 알고 싶은 경우 사용자 및 장치   [영향이란?을 참조하세요.](#whats-the-user-and-device-impact)</span><span class="sxs-lookup"><span data-stu-id="5d3ff-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="5d3ff-115">모바일 장치 지우기</span><span class="sxs-lookup"><span data-stu-id="5d3ff-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="5d3ff-116"> [Microsoft 365 관리 센터로 이동하세요.](../../admin/admin-overview/about-the-admin-center.md)</span><span class="sxs-lookup"><span data-stu-id="5d3ff-116">Go to the [Microsoft 365 admin center](../../admin/admin-overview/about-the-admin-center.md).</span></span>

2. <span data-ttu-id="5d3ff-117">검색 필드에 모바일 장치 관리를 입력하고 결과 목록에서 **모바일** 장치 관리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span>

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="기본 Mobility 및 Secruity 모바일 장치 관리 옵션":::

3. <span data-ttu-id="5d3ff-119">장치 **관리를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d3ff-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="5d3ff-120">초기화 할 장치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="5d3ff-121">관리를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d3ff-121">Select **Manage**.</span></span>

6. <span data-ttu-id="5d3ff-122">원하는 원격 초기화 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="5d3ff-123">전체 지우기를 적용하고 장치를 공장 설정으로 복원하려면 초기화 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d3ff-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="5d3ff-124">선택적으로 지우고 Microsoft 365 조직 정보만 삭제하려면 회사 데이터 **제거를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d3ff-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="5d3ff-125">조직에서 장치를 제거하려면 장치 **제거 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="5d3ff-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="5d3ff-126">**예** 를 선택하여 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="5d3ff-127">작동 여부는 어떻게 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="5d3ff-127">How do I know it worked?</span></span>

<span data-ttu-id="5d3ff-128">관리되는 장치 목록에 모바일 장치가 더 이상 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="5d3ff-129">장치를 지우는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="5d3ff-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="5d3ff-130">이러한 이유로 장치 지우기:</span><span class="sxs-lookup"><span data-stu-id="5d3ff-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="5d3ff-131">스마트폰 및 태블릿과 같은 모바일 장치는 점점 더 완전한 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="5d3ff-132">즉, 사용자가 개인 식별 또는 기밀 통신과 같은 중요한 회사 정보를 저장하고 이동 중 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="5d3ff-133">이러한 모바일 장치 중 하나를 분실하거나 도난당한 경우 장치를 지우면 조직의 정보가 잘못된 손에서 끝나지 않도록 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="5d3ff-134">사용자가 기본 이동성 및 보안에 등록된 개인 장치를 사용하여 조직을 떠나는 경우 공장 초기화 작업을 수행하여 조직 정보가 해당 사용자와 함께 이동하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="5d3ff-135">조직에서 사용자에게 모바일 장치를 제공하는 경우 장치를 수시로 다시 재배치해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="5d3ff-136">새 사용자에게 할당하기 전에 디바이스에서 공장 초기화 작업을 수행하면 이전 소유자의 중요한 정보가 삭제되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="5d3ff-137">사용자 및 디바이스가 미치는 영향</span><span class="sxs-lookup"><span data-stu-id="5d3ff-137">What's the user and device impact?</span></span>

<span data-ttu-id="5d3ff-138">초기화는 모바일 장치로 즉시 전송됩니다. 장치는 Azure Active Directory에서 호환되지 않는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="5d3ff-139">장치를 공장 기본값으로 다시 설정하면 모든 데이터가 제거되는 반면, 다음 표에서는 회사 데이터를 제거할 때 각 장치 유형에 대해 제거되는 콘텐츠에 대해 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="5d3ff-140">**콘텐츠 영향**</span><span class="sxs-lookup"><span data-stu-id="5d3ff-140">**Content impact**</span></span>|<span data-ttu-id="5d3ff-141">**iOS 10 이상**</span><span class="sxs-lookup"><span data-stu-id="5d3ff-141">**iOS 10 and later**</span></span>|<span data-ttu-id="5d3ff-142">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="5d3ff-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5d3ff-143">디바이스가 Intune 앱 보호 정책에 의해 보호되는 경우 Microsoft 365 앱 데이터가 지워지기</span><span class="sxs-lookup"><span data-stu-id="5d3ff-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="5d3ff-144">앱이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-144">The apps aren't removed.</span></span> <span data-ttu-id="5d3ff-145">MAM(모바일 응용 프로그램 관리) 정책으로 보호되지 않는 장치의 경우 Outlook 및 OneDrive는 캐시된 데이터를 제거하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="5d3ff-146">**참고** Intune 앱 보호 정책을 적용하려면 Intune 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="5d3ff-147">예</span><span class="sxs-lookup"><span data-stu-id="5d3ff-147">Yes</span></span>|<span data-ttu-id="5d3ff-148">예</span><span class="sxs-lookup"><span data-stu-id="5d3ff-148">Yes</span></span>|
|<span data-ttu-id="5d3ff-149">기본 모바일 및 보안에서 장치에 적용한 정책 설정은 더 이상 적용되지 않습니다. 사용자는 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="5d3ff-150">예</span><span class="sxs-lookup"><span data-stu-id="5d3ff-150">Yes</span></span>|<span data-ttu-id="5d3ff-151">예</span><span class="sxs-lookup"><span data-stu-id="5d3ff-151">Yes</span></span>|
|<span data-ttu-id="5d3ff-152">기본 Mobility and Security에서 만든 전자 메일 프로필이 제거되고 장치에서 캐시된 전자 메일이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="5d3ff-153">예</span><span class="sxs-lookup"><span data-stu-id="5d3ff-153">Yes</span></span>|<span data-ttu-id="5d3ff-154">해당 없음</span><span class="sxs-lookup"><span data-stu-id="5d3ff-154">N/A</span></span>|
>[!NOTE]
><span data-ttu-id="5d3ff-155">회사 포털 앱은 iOS용 앱 스토어 및 Android 디바이스용 Play 스토어에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d3ff-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5d3ff-156">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5d3ff-156">Related topics</span></span>

[<span data-ttu-id="5d3ff-157">기본 이동성 및 보안 설정</span><span class="sxs-lookup"><span data-stu-id="5d3ff-157">Set up Basic Mobility and Security</span></span>](set-up.md)
