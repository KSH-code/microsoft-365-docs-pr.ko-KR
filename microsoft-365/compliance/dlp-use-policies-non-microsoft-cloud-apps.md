---
title: Microsoft가 아닌 클라우드 앱에 데이터 손실 방지 정책 사용(미리 보기)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: Microsoft가 아닌 클라우드 앱에 대해 dlp 정책을 사용하는 방법을 배워야 합니다.
ms.openlocfilehash: ca522b5accbd2c08e80b0ce63871179ff64bbcc8
ms.sourcegitcommit: 46b77a41dfcc0ee80e2b89a7aa49e9bbe5deae5a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2021
ms.locfileid: "53149157"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="34d5e-103">Microsoft가 아닌 클라우드 앱에 데이터 손실 방지 정책 사용(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="34d5e-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="34d5e-104">Microsoft가 아닌 클라우드 앱에 대한 DLP(데이터 손실 방지) 정책은 Microsoft 365 DLP 제품군의 일부입니다. 이러한 기능을 사용하여 여러 서비스에서 중요한 항목을 검색하고 보호할 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d5e-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="34d5e-105">모든 Microsoft DLP 제공에 대한 자세한 내용은 데이터 손실 방지에 대한 자세한 [정보를 참조하세요.](dlp-learn-about-dlp.md)</span><span class="sxs-lookup"><span data-stu-id="34d5e-105">For more information about all Microsoft DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="34d5e-106">DLP 정책을 사용하여 Microsoft가 아닌 클라우드 앱에 중요한 항목이 사용되는 경우를 모니터링하고 Microsoft가 아닌 클라우드 앱을 통해 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d5e-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="34d5e-107">이러한 정책을 사용하면 정책이 올바르게 사용 및 보호되도록 하는 데 필요한 가시성과 제어가 제공될 수 있으며, 이를 통해 손상될 수 있는 위험한 동작을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d5e-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="34d5e-108">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="34d5e-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="34d5e-109">SKU/구독 라이선싱</span><span class="sxs-lookup"><span data-stu-id="34d5e-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="34d5e-110">Microsoft가 아닌 클라우드 앱에 DLP 정책을 사용하려면 먼저 Microsoft 365 추가 기능을 선택합니다. [](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)</span><span class="sxs-lookup"><span data-stu-id="34d5e-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="34d5e-111">이 기능에 액세스하고 사용하려면 다음 구독 또는 추가 기능 중 하나만 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="34d5e-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="34d5e-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="34d5e-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="34d5e-113">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="34d5e-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="34d5e-114">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="34d5e-114">Microsoft 365 E5 Security</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="34d5e-115">사용자 환경 Cloud App Security 준비</span><span class="sxs-lookup"><span data-stu-id="34d5e-115">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="34d5e-116">Microsoft가 아닌 클라우드 앱에 대한 DLP 정책은 DLP Cloud App Security 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="34d5e-116">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="34d5e-117">이 기능을 사용하기 위해 사용자 환경의 Cloud App Security 합니다.</span><span class="sxs-lookup"><span data-stu-id="34d5e-117">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="34d5e-118">지침은 앱에 대한 즉각적인 가시성, 보호 [및 거버넌스 작업 설정 을 참조하세요.](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)</span><span class="sxs-lookup"><span data-stu-id="34d5e-118">For instructions, see [Set instant visibility, protection, and governance actions for your apps](/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="34d5e-119">커넥트 아닌 클라우드 앱 다운로드</span><span class="sxs-lookup"><span data-stu-id="34d5e-119">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="34d5e-120">DLP 정책을 Microsoft가 아닌 특정 클라우드 앱에 사용하려면 앱이 앱에 연결되어 있어야 Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="34d5e-120">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="34d5e-121">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="34d5e-121">For information, see:</span></span>

- [<span data-ttu-id="34d5e-122">커넥트 Box</span><span class="sxs-lookup"><span data-stu-id="34d5e-122">Connect Box</span></span>](/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="34d5e-123">커넥트 Dropbox</span><span class="sxs-lookup"><span data-stu-id="34d5e-123">Connect Dropbox</span></span>](/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="34d5e-124">커넥트 G-Suite</span><span class="sxs-lookup"><span data-stu-id="34d5e-124">Connect G-Suite</span></span>](/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="34d5e-125">커넥트 Salesforce</span><span class="sxs-lookup"><span data-stu-id="34d5e-125">Connect Salesforce</span></span>](/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="34d5e-126">커넥트 Cisco Webex</span><span class="sxs-lookup"><span data-stu-id="34d5e-126">Connect Cisco Webex</span></span>](/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="34d5e-127">클라우드 앱에 연결한 Cloud App Security DLP 정책을 Microsoft 365 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d5e-127">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

>[!NOTE]
><span data-ttu-id="34d5e-128">Microsoft 클라우드 앱에 대한 DLP 정책을 Microsoft Cloud App Security 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d5e-128">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="34d5e-129">그러나 Microsoft 클라우드 앱에 대한 DLP 정책을 Microsoft 365 관리하기 위해 이 정책을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="34d5e-129">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="34d5e-130">Microsoft가 아닌 클라우드 앱에 대한 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="34d5e-130">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="34d5e-131">DLP 정책의 위치를 선택하면 해당 위치를 **Microsoft Cloud App Security.**</span><span class="sxs-lookup"><span data-stu-id="34d5e-131">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="34d5e-132">특정 앱 또는 인스턴스를 선택하려면 인스턴스 **선택 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="34d5e-132">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="34d5e-133">인스턴스를 선택하지 않은 경우 정책은 테넌트의 모든 연결된 앱을 Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="34d5e-133">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![정책을 적용할 위치](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US 및 Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="34d5e-136">지원되는 모든 비 Microsoft 클라우드 앱에 대해 다양한 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d5e-136">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="34d5e-137">모든 앱에 대해 가능한 작업이 다릅니다(클라우드 앱 API에 따라 다름).</span><span class="sxs-lookup"><span data-stu-id="34d5e-137">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![규칙 만들기](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="34d5e-139">DLP 정책에서 규칙을 만들 때 Microsoft가 아닌 클라우드 앱에 대한 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="34d5e-139">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="34d5e-140">타사 앱을 제한하려면 타사 앱 **제한을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="34d5e-140">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![타사 앱 제한](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

><span data-ttu-id="34d5e-142">[참고] Microsoft 앱이 아닌 앱에 적용되는 DLP 정책은 Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="34d5e-142">[NOTE] DLP policies applied to non-Microsoft apps use Microsoft Cloud App Security.</span></span> <span data-ttu-id="34d5e-143">Microsoft가 아닌 앱에 대한 DLP 정책을 만들면 해당 앱에서 동일한 정책이 Microsoft Cloud App Security.</span><span class="sxs-lookup"><span data-stu-id="34d5e-143">When the DLP policy for a non-Microsoft app is created, the same policy will be automatically created in Microsoft Cloud App Security.</span></span>

<span data-ttu-id="34d5e-144">DLP 정책을 만들고 구성하는 데 대한 자세한 내용은 [Create test and tune a DLP policy 를 참조하십시오.](./create-test-tune-dlp-policy.md?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="34d5e-144">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](./create-test-tune-dlp-policy.md?view=o365-worldwide).</span></span>

## <a name="see-also"></a><span data-ttu-id="34d5e-145">참고 항목</span><span class="sxs-lookup"><span data-stu-id="34d5e-145">See Also</span></span>

- [<span data-ttu-id="34d5e-146">테스트 만들기 및 DLP 정책 조정</span><span class="sxs-lookup"><span data-stu-id="34d5e-146">Create test and tune a DLP policy</span></span>](./create-test-tune-dlp-policy.md?view=o365-worldwide)
- [<span data-ttu-id="34d5e-147">기본 DLP 정책을 사용하여 시작</span><span class="sxs-lookup"><span data-stu-id="34d5e-147">Get started with the default DLP policy</span></span>](./get-started-with-the-default-dlp-policy.md?view=o365-worldwide)
- [<span data-ttu-id="34d5e-148">서식 파일에서 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="34d5e-148">Create a DLP policy from a template</span></span>](./create-a-dlp-policy-from-a-template.md?view=o365-worldwide)
