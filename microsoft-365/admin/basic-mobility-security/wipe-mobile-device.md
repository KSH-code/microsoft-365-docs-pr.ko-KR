---
title: 기본 Mobility and Security에서 모바일 장치 지우기
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
description: 기본 제공 되는 기본 모바일 및 보안을 사용 하 여 등록 된 장치에서 정보를 제거 합니다.
ms.openlocfilehash: 4d854c7d4d81cd0b49ec7f81a49de5478b08f049
ms.sourcegitcommit: 2179abfe0b7a8bea917eb1c1057ed3795bdf91e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2020
ms.locfileid: "47337005"
---
# <a name="wipe-a-mobile-device-in-basic-mobility-and-security"></a><span data-ttu-id="bb21c-103">기본 Mobility and Security에서 모바일 장치 지우기</span><span class="sxs-lookup"><span data-stu-id="bb21c-103">Wipe a mobile device in Basic Mobility and Security</span></span>

<span data-ttu-id="bb21c-104">Microsoft 365에 기본 제공 되는 기본 모바일 및 보안을 사용 하 여 조직 정보만 제거 하거나, 공장 초기화를 수행 하 여 모바일 장치에서 모든 정보를 삭제 하 고 공장 설정으로 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-104">You can use built-in Basic Mobility and Security for Microsoft 365 to remove only organizational information, or to perform a factory reset to delete all information from a mobile device and restore it to factory settings.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="bb21c-105">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="bb21c-105">Before you begin</span></span>

<span data-ttu-id="bb21c-106">모바일 장치는 중요 한 조직 정보를 저장 하 고 조직의 Microsoft 365 리소스에 대 한 액세스를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-106">Mobile devices can store sensitive organizational information and provide access to your organization's Microsoft 365 resources.</span></span> <span data-ttu-id="bb21c-107">조직의 정보를 보호 하려면 다음을 수행 하 여 회사 데이터를 초기화 하거나 제거해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-107">To help protect your organization's information, you can do Factory reset or Remove company data:</span></span>
    
- <span data-ttu-id="bb21c-108">**공장 초기화**: 설치 된 응용 프로그램, 사진 및 개인 정보를 포함 하 여 사용자의 모바일 장치에 있는 모든 데이터를 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-108">**Factory reset**: Deletes all data on a user's mobile device, including installed applications, photos, and personal information.</span></span> <span data-ttu-id="bb21c-109">초기화가 완료 되 면 장치가 공장 설정으로 복원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-109">When the wipe is complete, the device is restored to its factory settings.</span></span>
    
- <span data-ttu-id="bb21c-110">**회사 데이터 제거**: 조직 데이터만 제거 하 고 설치 된 응용 프로그램, 사진 및 개인 정보를 사용자의 모바일 장치에 남겨 둡니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-110">**Remove company data**: Removes only organization data and leaves installed applications, photos, and personal information on a user's mobile device.</span></span>   

- <span data-ttu-id="bb21c-111">**장치가 초기화 되 면 (공장 초기화 또는 회사 데이터 제거)** 장치가 관리 되는 장치 목록에서 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-111">**When a device is wiped (Factory Reset or Remove Company Data)**, the device is removed from the list of managed devices.</span></span>
    
- <span data-ttu-id="bb21c-112">**자동으로 장치 다시 설정**: 사용자가 특정 횟수 만큼 장치 암호를 입력 하지 못한 후 장치를 자동으로 초기화 하는 기본 이동성 및 보안 정책을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-112">**Automatically reset a device**: You can set up a Basic Mobility and Security policy that automatically factory resets a device after the user unsuccessfully tries to enter the device password a specific number of times.</span></span> <span data-ttu-id="bb21c-113">이렇게 하려면 [기본 이동성 및 보안에서 장치 보안 정책 만들기](create-device-security-policies-in-basic-mmobility-and-security.md)의 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-113">To do this, follow the steps in [Create device security policies in basic mobility and security](create-device-security-policies-in-basic-mmobility-and-security.md).</span></span>
    
- <span data-ttu-id="bb21c-114">장치를 정리할 때 **사용자 환경을 확인 하려면**   [사용자 및 장치 영향](#whats-the-user-and-device-impact)을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="bb21c-114">**If you want to know the user experience** when you wipe their device, see  [What's the user and device impact?](#whats-the-user-and-device-impact).</span></span>   

## <a name="wipe-a-mobile-device"></a><span data-ttu-id="bb21c-115">모바일 장치 초기화</span><span class="sxs-lookup"><span data-stu-id="bb21c-115">Wipe a mobile device</span></span>

1. <span data-ttu-id="bb21c-116"> [Microsoft 365 관리 센터로](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-116">Go to the [Microsoft 365 admin center](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23).</span></span>
    
2. <span data-ttu-id="bb21c-117">검색 필드에 모바일 장치 관리를 입력 하 고 결과 목록에서 **모바일 장치 관리** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-117">Type Mobile Device Management into the search field, and select **Mobile Device Management** from the list of results.</span></span> 

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="기본 이동성 및 Secruity 모바일 장치 관리 옵션":::

3. <span data-ttu-id="bb21c-119">**장치 관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-119">Select **Manage devices**.</span></span>

4. <span data-ttu-id="bb21c-120">초기화 할 장치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-120">Select the device you want to wipe.</span></span>

5. <span data-ttu-id="bb21c-121">**관리**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-121">Select **Manage**.</span></span>

6. <span data-ttu-id="bb21c-122">원하는 원격 초기화 유형을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-122">Select the type of remote wipe you want to do.</span></span>

    - <span data-ttu-id="bb21c-123">전체 초기화를 수행 하 고 장치를 공장 설정으로 복원 하려면 **공장 초기화**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-123">To do a full wipe and restore the device to its factory settings, select **Factory reset**.</span></span>
    - <span data-ttu-id="bb21c-124">선택적으로 지우기를 수행 하 고 Microsoft 365 조직 정보만 삭제 하려면 **회사 데이터 제거**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-124">To do a selective wipe and delete only Microsoft 365 organization information, select **Remove company data**.</span></span>
    - <span data-ttu-id="bb21c-125">조직에서 디바이스를 제거 하려면 **장치 제거**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-125">To remove the device from your organization, select **Remove device**.</span></span>

7. <span data-ttu-id="bb21c-126">**예**를 선택하여 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-126">Select **Yes** to confirm.</span></span>

## <a name="how-do-i-know-it-worked"></a><span data-ttu-id="bb21c-127">작동 여부는 어떻게 확인 하나요?</span><span class="sxs-lookup"><span data-stu-id="bb21c-127">How do I know it worked?</span></span>

<span data-ttu-id="bb21c-128">관리 되는 장치 목록에 모바일 장치가 더 이상 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-128">You no longer see the mobile device in the list of managed devices.</span></span>

## <a name="why-would-you-want-to-wipe-a-device"></a><span data-ttu-id="bb21c-129">장치를 초기화 하는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="bb21c-129">Why would you want to wipe a device?</span></span>

<span data-ttu-id="bb21c-130">다음과 같은 이유로 장치를 정리 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-130">Wipe a device for these reasons:</span></span>

- <span data-ttu-id="bb21c-131">스마트폰 및 태블릿과 같은 모바일 장치가 항상 모든 기능을 제공 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-131">Mobile devices like smartphones and tablets are becoming more full-featured all the time.</span></span> <span data-ttu-id="bb21c-132">즉, 사용자가 개인 id 또는 기밀 통신과 같은 중요 한 회사 정보를 보다 쉽게 저장 하 고 이동 중에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-132">This means it’s easier for your users to store sensitive corporate information such as personal identification or confidential communications and access it on the go.</span></span> <span data-ttu-id="bb21c-133">이러한 모바일 장치 중 하나를 분실 하거나 도난당 한 경우 장치를 초기화 하면 조직의 정보가 잘못 된 손에 전달 되는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-133">If one of these mobile devices is lost or stolen, wiping the device can help prevent your organization’s information from ending up in the wrong hands.</span></span>
- <span data-ttu-id="bb21c-134">사용자가 기본 Mobility and Security에 등록 되어 있는 개인 장치로 조직을 떠나는 경우, 공장 초기화를 수행 하 여 조직 정보가 해당 사용자와 함께 이동 하지 못하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-134">When a user leaves the organization with a personal device that is enrolled in Basic Mobility and Security, you can help prevent organizational information from going with that user by performing a factory reset.</span></span>
- <span data-ttu-id="bb21c-135">조직에서 사용자에 게 모바일 장치를 제공 하는 경우 시간에서 시간까지 장치를 다시 할당 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-135">If your organization provides mobile devices to users, you might need to reassign devices from time to time.</span></span> <span data-ttu-id="bb21c-136">장치를 새 사용자에 게 할당 하기 전에 디바이스에서 초기화를 수행 하면 이전 소유자의 중요 한 정보를 삭제 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-136">Doing a Factory Reset on a device before assigning it to a new user helps ensures that any sensitive information from the previous owner is deleted.</span></span>

## <a name="whats-the-user-and-device-impact"></a><span data-ttu-id="bb21c-137">사용자 및 장치에 미치는 영향은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="bb21c-137">What's the user and device impact?</span></span>

<span data-ttu-id="bb21c-138">초기화가 모바일 장치로 즉시 전송 되 고 디바이스가 Azure active directory에서 비규격으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-138">The wipe is sent immediately to the mobile device and the device is marked as not compliant in Azure active directory.</span></span> <span data-ttu-id="bb21c-139">장치를 출고시 기본값으로 다시 설정 하면 모든 데이터가 제거 되지만, 다음 표에서는 회사 데이터를 제거할 때 각 장치 유형에 서 제거 되는 콘텐츠를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-139">While all data is removed when a device is reset to factory defaults, the following table describes what content is removed for each device type when a device when you remove company data.</span></span>

|<span data-ttu-id="bb21c-140">**Content  ace**</span><span class="sxs-lookup"><span data-stu-id="bb21c-140">**Content impace**</span></span>|<span data-ttu-id="bb21c-141">**iOS 10 이상**</span><span class="sxs-lookup"><span data-stu-id="bb21c-141">**iOS 10 and later**</span></span>|<span data-ttu-id="bb21c-142">**Android 5 이상**</span><span class="sxs-lookup"><span data-stu-id="bb21c-142">**Android 5 and later**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bb21c-143">Microsoft 365 앱 데이터는 Intune 앱 보호 정책에 의해 보호 되는 장치를 초기화 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-143">Microsoft 365 app data is wiped if the device is protected by Intune App Protection policies.</span></span> <span data-ttu-id="bb21c-144">앱이 제거 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-144">The apps aren't removed.</span></span> <span data-ttu-id="bb21c-145">MAM (모바일 응용 프로그램 관리) 정책에 의해 보호 되지 않는 장치의 경우 Outlook 및 OneDrive에서 캐시 된 데이터를 제거 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-145">For devices not protected by Mobile Application Management (MAM) policies, Outlook and OneDrive won't remove cached data.</span></span><br/><span data-ttu-id="bb21c-146">**참고 사항** Intune 앱 보호 정책을 적용 하려면 Intune 라이선스가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-146">**Note** For applying Intune App protection policies you must have an Intune license.</span></span>|<span data-ttu-id="bb21c-147">예</span><span class="sxs-lookup"><span data-stu-id="bb21c-147">Yes</span></span>|<span data-ttu-id="bb21c-148">예</span><span class="sxs-lookup"><span data-stu-id="bb21c-148">Yes</span></span>|
|<span data-ttu-id="bb21c-149">기본 이동성 및 장치에 대 한 보안에 의해 적용 되는 정책 설정이 더 이상 적용 되지 않습니다. 사용자가 설정을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-149">Policy settings applied by Basic Mobility and Security to devices are no longer enforced; users can change the settings.</span></span>|<span data-ttu-id="bb21c-150">예</span><span class="sxs-lookup"><span data-stu-id="bb21c-150">Yes</span></span>|<span data-ttu-id="bb21c-151">예</span><span class="sxs-lookup"><span data-stu-id="bb21c-151">Yes</span></span>|
|<span data-ttu-id="bb21c-152">기본 이동성 및 보안에 의해 생성 된 전자 메일 프로필이 제거 되 고 장치의 캐시 된 전자 메일이 삭제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-152">Email profiles created by Basic Mobility and Security are removed and cached email on the device is deleted.</span></span>|<span data-ttu-id="bb21c-153">예</span><span class="sxs-lookup"><span data-stu-id="bb21c-153">Yes</span></span>|<span data-ttu-id="bb21c-154">해당 없음</span><span class="sxs-lookup"><span data-stu-id="bb21c-154">N/A</span></span>|
>[!NOTE] 
><span data-ttu-id="bb21c-155">회사 포털 앱은 iOS 용 앱 스토어 및 Android 장치용 재생 저장소에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb21c-155">Company Portal app is available at the App Store for iOS and the Play Store for Android devices.</span></span>

## <a name="related-topics"></a><span data-ttu-id="bb21c-156">관련 항목</span><span class="sxs-lookup"><span data-stu-id="bb21c-156">Related topics</span></span>

[<span data-ttu-id="bb21c-157">기본 이동성 및 보안 설정</span><span class="sxs-lookup"><span data-stu-id="bb21c-157">Set up Basic Mobility and Security</span></span>](set-up-basic-mobility-and-security.md)