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
description: Microsoft가 아닌 클라우드 앱에 대해 dlp 정책을 사용하는 방법을 학습합니다.
ms.openlocfilehash: 0b588bf27738a0f9a8078999311294f74e5193c0
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48649659"
---
# <a name="use-data-loss-prevention-policies-for-non-microsoft-cloud-apps-preview"></a><span data-ttu-id="1710b-103">Microsoft가 아닌 클라우드 앱에 데이터 손실 방지 정책 사용(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="1710b-103">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>

<span data-ttu-id="1710b-104">Microsoft가 아닌 클라우드 앱에 대한 DLP(데이터 손실 방지) 정책은 Microsoft 365 DLP 기능 제품군의 일부입니다. 이러한 기능을 사용하여 Microsoft 365 서비스에서 중요한 항목을 검색하고 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1710b-104">Data loss prevention (DLP) policies to non-Microsoft cloud apps are part of the Microsoft 365 DLP suite of features; using these features, you can discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="1710b-105">모든 Microsoft DLP 제공에 대한 자세한 내용은 데이터 손실 방지 [개요를 참조하세요.](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="1710b-105">For more information about all Microsoft DLP offerings, see [Overview of data loss prevention](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide).</span></span>

<span data-ttu-id="1710b-106">DLP 정책을 사용하여 Microsoft가 아닌 클라우드 앱에 중요한 항목이 사용되는 경우를 모니터링하고 Microsoft가 아닌 클라우드 앱을 통해 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1710b-106">You can use DLP policies to non-Microsoft cloud apps to monitor and detect when sensitive items are used and shared via non-Microsoft cloud apps.</span></span> <span data-ttu-id="1710b-107">이러한 정책을 사용하면 정책이 올바르게 사용 및 보호되도록 하는 데 필요한 가시성과 제어가 제공될 수 있으며 손상될 수 있는 위험한 동작을 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1710b-107">Using these policies gives you the visibility and control that you need to ensure that they're correctly used and protected, and it helps prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1710b-108">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="1710b-108">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="1710b-109">SKU/구독 라이선싱</span><span class="sxs-lookup"><span data-stu-id="1710b-109">SKU/subscriptions licensing</span></span>

<span data-ttu-id="1710b-110">DLP 정책을 Microsoft가 아닌 클라우드 앱에 사용하려면 먼저 [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) 구독 및 추가 기능을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="1710b-110">Before you start using DLP policies to non-Microsoft cloud apps, confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="1710b-111">이 기능에 액세스하고 사용하려면 다음 구독 또는 추가 기능 중 하나가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1710b-111">To access and use this functionality, you must have one of these subscriptions or add-ons:</span></span>

- <span data-ttu-id="1710b-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1710b-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="1710b-113">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="1710b-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="1710b-114">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="1710b-114">Microsoft 365 E5 Security</span></span>

### <a name="prepare-your-cloud-app-security-environment"></a><span data-ttu-id="1710b-115">Cloud App Security 환경 준비</span><span class="sxs-lookup"><span data-stu-id="1710b-115">Prepare your Cloud App Security environment</span></span>

<span data-ttu-id="1710b-116">Microsoft가 아닌 클라우드 앱에 대한 DLP 정책은 Cloud App Security DLP 기능을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1710b-116">DLP policies to non-Microsoft cloud apps use Cloud App Security DLP capabilities.</span></span> <span data-ttu-id="1710b-117">클라우드 앱 보안 환경을 준비해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1710b-117">To use it, you should prepare your Cloud App Security environment.</span></span> <span data-ttu-id="1710b-118">지침은 앱에 대한 [인스턴트 가시성, 보호 및 거버넌스 작업 설정을 참조하세요.](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps)</span><span class="sxs-lookup"><span data-stu-id="1710b-118">For instructions, see [Set instant visibility, protection, and governance actions for your apps](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security#step-1-set-instant-visibility-protection-and-governance-actions-for-your-apps).</span></span>

### <a name="connect-a-non-microsoft-cloud-app"></a><span data-ttu-id="1710b-119">Microsoft가 아닌 클라우드 앱 연결</span><span class="sxs-lookup"><span data-stu-id="1710b-119">Connect a non-Microsoft cloud app</span></span>

<span data-ttu-id="1710b-120">DLP 정책을 Microsoft가 아닌 특정 클라우드 앱에 사용하려면 앱이 Cloud App Security에 연결되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1710b-120">To use DLP policy to a specific non-Microsoft cloud app, the app must be connected to Cloud App Security.</span></span> <span data-ttu-id="1710b-121">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1710b-121">For information, see:</span></span>

- [<span data-ttu-id="1710b-122">Connect Box</span><span class="sxs-lookup"><span data-stu-id="1710b-122">Connect Box</span></span>](https://docs.microsoft.com/cloud-app-security/connect-box-to-microsoft-cloud-app-security)
- [<span data-ttu-id="1710b-123">Dropbox 연결</span><span class="sxs-lookup"><span data-stu-id="1710b-123">Connect Dropbox</span></span>](https://docs.microsoft.com/cloud-app-security/connect-dropbox-to-microsoft-cloud-app-security)
- [<span data-ttu-id="1710b-124">G-Suite 연결</span><span class="sxs-lookup"><span data-stu-id="1710b-124">Connect G-Suite</span></span>](https://docs.microsoft.com/cloud-app-security/connect-google-apps-to-microsoft-cloud-app-security)
- [<span data-ttu-id="1710b-125">Connect Salesforce</span><span class="sxs-lookup"><span data-stu-id="1710b-125">Connect Salesforce</span></span>](https://docs.microsoft.com/cloud-app-security/connect-salesforce-to-microsoft-cloud-app-security)
- [<span data-ttu-id="1710b-126">Cisco Webex 연결</span><span class="sxs-lookup"><span data-stu-id="1710b-126">Connect Cisco Webex</span></span>](https://docs.microsoft.com/cloud-app-security/connect-webex-to-microsoft-cloud-app-security)

<span data-ttu-id="1710b-127">클라우드 앱을 Cloud App Security에 연결한 후 클라우드 앱에 대한 Microsoft 365 DLP 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1710b-127">After you connect your cloud apps to Cloud App Security, you can create Microsoft 365 DLP policies for them.</span></span>

>[!NOTE]
><span data-ttu-id="1710b-128">Microsoft Cloud App Security를 사용하여 Microsoft 클라우드 앱에 대한 DLP 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1710b-128">It's also possible to use Microsoft Cloud App Security to create DLP policies to Microsoft cloud apps.</span></span> <span data-ttu-id="1710b-129">그러나 Microsoft 365를 사용하여 Microsoft 클라우드 앱에 대한 DLP 정책을 만들고 관리하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1710b-129">However, it's recommended to use Microsoft 365 to create and manage DLP policies to Microsoft cloud apps.</span></span>

## <a name="create-a-dlp-policy-to-a-non-microsoft-cloud-app"></a><span data-ttu-id="1710b-130">Microsoft가 아닌 클라우드 앱에 대한 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="1710b-130">Create a DLP policy to a non-Microsoft cloud app</span></span>

<span data-ttu-id="1710b-131">DLP 정책의 위치를 선택하면 Microsoft Cloud **App Security** 위치를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1710b-131">When you select a location for the DLP policy, turn on the **Microsoft Cloud App Security** location.</span></span>

- <span data-ttu-id="1710b-132">특정 앱 또는 인스턴스를 선택하려면 인스턴스 **선택을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1710b-132">To select a specific app or instance, select **Choose instance**.</span></span>
- <span data-ttu-id="1710b-133">인스턴스를 선택하지 않은 경우 정책은 Microsoft Cloud App Security 테넌트의 연결된 모든 앱을 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1710b-133">If you don't select an instance, the policy uses all connected apps in your Microsoft Cloud App Security tenant.</span></span>

   ![정책을 적용할 위치](../media/1-dlp-non-microsoft-cloud-app-choose-instance.png)

   ![Box-US 및 Box-General](../media/2-dlp-non-microsoft-cloud-app-box.png)

<span data-ttu-id="1710b-136">지원되는 모든 비 Microsoft 클라우드 앱에 대해 다양한 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1710b-136">You can choose various actions for every supported non-Microsoft cloud app.</span></span> <span data-ttu-id="1710b-137">모든 앱에 대해 가능한 작업이 여러 가지 있습니다(클라우드 앱 API에 따라 다름).</span><span class="sxs-lookup"><span data-stu-id="1710b-137">For every app, there are different possible actions (depends on the cloud app API).</span></span>

![규칙 만들기](../media/3-dlp-non-microsoft-cloud-app-create-rule.png)

<span data-ttu-id="1710b-139">DLP 정책에서 규칙을 만들 때 Microsoft가 아닌 클라우드 앱에 대한 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1710b-139">When you create a rule in the DLP policy, you can select an action for non-Microsoft cloud apps.</span></span> <span data-ttu-id="1710b-140">타사 앱을 제한하려면 타사 앱 **제한을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="1710b-140">To restrict third-party apps, select **Restrict Third Party Apps**.</span></span>

![타사 앱 제한](../media/4-dlp-non-microsoft-cloud-app-restrict-third-party-apps.png)

<span data-ttu-id="1710b-142">DLP 정책 만들기 및 구성에 대한 자세한 내용은 테스트 만들기 및 DLP 정책 [조정을 참조하십시오.](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="1710b-142">For information about creating and configuring DLP policies, see [Create test and tune a DLP policy](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide).</span></span>

## <a name="see-also"></a><span data-ttu-id="1710b-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1710b-143">See Also</span></span>

- [<span data-ttu-id="1710b-144">테스트 만들기 및 DLP 정책 조정</span><span class="sxs-lookup"><span data-stu-id="1710b-144">Create test and tune a DLP policy</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-test-tune-dlp-policy?view=o365-worldwide)
- [<span data-ttu-id="1710b-145">기본 DLP 정책을 사용하여 시작</span><span class="sxs-lookup"><span data-stu-id="1710b-145">Get started with the default DLP policy</span></span>](https://docs.microsoft.com/microsoft-365/compliance/get-started-with-the-default-dlp-policy?view=o365-worldwide)
- [<span data-ttu-id="1710b-146">서식 파일에서 DLP 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="1710b-146">Create a DLP policy from a template</span></span>](https://docs.microsoft.com/microsoft-365/compliance/create-a-dlp-policy-from-a-template?view=o365-worldwide)
