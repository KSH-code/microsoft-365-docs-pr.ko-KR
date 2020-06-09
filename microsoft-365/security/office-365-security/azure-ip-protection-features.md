---
title: Azure Information Protection의 보호 기능을 통해 기존 테 넌 트에 배포
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 Azure Information Protection의 보호 기능을 수행 하는 변경 사항에 대해 설명 합니다.
ms.openlocfilehash: c2f386e17d3c0da74f360a7b1262a2f32dbf92cc
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616737"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a><span data-ttu-id="73109-103">Azure Information Protection의 보호 기능을 통해 기존 테 넌 트에 배포</span><span class="sxs-lookup"><span data-stu-id="73109-103">Protection features in Azure Information Protection rolling out to existing tenants</span></span>

<span data-ttu-id="73109-104">정보를 보호 하는 초기 단계를 지원 하기 위해 7 월 2018 일부터 모든 Azure Information Protection 적합 한 테 넌 트에는 기본적으로 Azure Information Protection의 보호 기능이 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73109-104">To help with the initial step in protecting your information, starting July 2018 all Azure Information Protection eligible tenants will have the protection features in Azure Information Protection turned on by default.</span></span> <span data-ttu-id="73109-105">Azure Information Protection의 보호 기능은 이전에는 Office 365에서 권한 관리 또는 Azure RMS로 알려져 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="73109-105">The protection features in Azure Information Protection were formerly known in Office 365 as Rights Management or Azure RMS.</span></span> <span data-ttu-id="73109-106">조직에 Office E3 서비스 계획 또는 서비스 계획이 더 높은 경우에는 이러한 기능을 롤아웃할 때 Azure Information Protection을 통해 정보를 보호 하기 시작할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73109-106">If your organization has an Office E3 service plan or a higher service plan you will now get a head start protecting information through Azure Information Protection when we roll out these features.</span></span>

## <a name="changes-beginning-july-1-2018"></a><span data-ttu-id="73109-107">2018 년 7 월 1 일부터 변경</span><span class="sxs-lookup"><span data-stu-id="73109-107">Changes beginning July 1, 2018</span></span>

<span data-ttu-id="73109-108">2018 년 7 월 1 일부 터 Microsoft는 다음 구독 계획 중 하나를 사용 하 여 모든 조직에 대해 Azure Information Protection의 보호 기능을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="73109-108">Starting July 1, 2018, Microsoft will enable the protection capability in Azure Information Protection for all organizations with one of the following subscription plans:</span></span>

- <span data-ttu-id="73109-109">Office 365 메시지 암호화는 Office 365 E3 및 E5, Microsoft E3 및 E5, Office 365 A1, A3, A5 및 Office 365 G3 및 G5의 일부로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73109-109">Office 365 Message Encryption is offered as part of Office 365 E3 and E5, Microsoft E3 and E5, Office 365 A1, A3, and A5, and Office 365 G3 and G5.</span></span> <span data-ttu-id="73109-110">Azure Information Protection에서 제공 하는 새로운 보호 기능을 수신 하기 위해 추가 라이선스가 필요 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73109-110">You do not need additional licenses to receive the new protection capabilities powered by Azure Information Protection.</span></span>

- <span data-ttu-id="73109-111">또한 다음 계획에 Azure Information Protection 계획 1을 추가 하 여 Exchange Online 계획 1, Exchange Online 계획 2, Office 365 F1, 365 Microsoft 365 Business Standard 또는 Office 365 Enterprise E1과 같은 새로운 Office 365 메시지 암호화 기능을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73109-111">You can also add Azure Information Protection Plan 1 to the following plans to receive the new Office 365 Message Encryption capabilities: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard, or Office 365 Enterprise E1.</span></span>

- <span data-ttu-id="73109-112">Office 365 메시지 암호화에서 각 사용자 benefiting 기능을 사용 하도록 허가 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73109-112">Each user benefiting from Office 365 Message Encryption needs to be licensed to be covered by the feature.</span></span>

- <span data-ttu-id="73109-113">전체 목록은 Office 365 메시지 암호화에 대 한 [Exchange Online 서비스 설명을](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="73109-113">For the full list, see the [Exchange Online service descriptions](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) for Office 365 Message Encryption.</span></span>

<span data-ttu-id="73109-114">테 넌 트 관리자는 Office 365 관리자 포털에서 보호 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73109-114">Tenant administrators can check the protection status in the Office 365 administrator portal.</span></span>

![Office 365의 권한 관리가 활성화 되었음을 보여 주는 스크린샷](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a><span data-ttu-id="73109-116">변경 되는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="73109-116">Why are we making this change?</span></span>

<span data-ttu-id="73109-117">Office 365 메시지 암호화는 Azure Information Protection의 보호 기능을 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="73109-117">Office 365 Message Encryption leverages the protection capabilities in Azure Information Protection.</span></span> <span data-ttu-id="73109-118">Office 365 메시지 암호화에 대 한 최신 개선 사항 및 Microsoft 365의 정보 보호에 대 한 폭넓은 투자가 제공 되므로, 조직에서 최대한 쉽게 보호 기능을 설정 하 고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73109-118">At the heart of the recent improvements to Office 365 Message Encryption and our broader investments to information protection in Microsoft 365, we are making it easier for organizations to turn on and use our protection capabilities, as historically, encryption technologies have been difficult to set up.</span></span> <span data-ttu-id="73109-119">기본적으로 Azure Information Protection의 보호 기능을 설정 하 여 중요 한 데이터를 빠르게 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73109-119">By turning on the protection features in Azure Information Protection by default, you can quickly get started to protect your sensitive data.</span></span>

## <a name="does-this-impact-me"></a><span data-ttu-id="73109-120">나에 게 영향을 줍니까?</span><span class="sxs-lookup"><span data-stu-id="73109-120">Does this impact me?</span></span>

<span data-ttu-id="73109-121">조직에서 적격 Office 365 라이선스를 구매한 경우이 변경으로 인해 테 넌 트가 영향을 받게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73109-121">If your organization has purchased an eligible Office 365 license, then your tenant will be impacted by this change.</span></span>

 <span data-ttu-id="73109-122">**중요 한!**</span><span class="sxs-lookup"><span data-stu-id="73109-122">**IMPORTANT!**</span></span> <span data-ttu-id="73109-123">온-프레미스 환경에서 AD RMS (Active Directory Rights Management Services)를 사용 하는 경우에는이 변경 내용을 즉시 옵트아웃 하거나 Azure Information Protection으로 마이그레이션해야 하 여 다음 30 일 이내에이 변경 내용을 롤아웃 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73109-123">If you're using Active Directory Rights Management Services (AD RMS) in your on-premises environment, you must either opt-out of this change immediately or migrate to Azure Information Protection before we roll out this change within the next 30 days.</span></span> <span data-ttu-id="73109-124">옵트아웃 하는 방법에 대 한 자세한 내용은 "use AD RMS, 옵트아웃 (opt out)"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="73109-124">For information on how to opt-out, see "I use AD RMS, how do I opt out?"</span></span> <span data-ttu-id="73109-125">이 문서의 뒷부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73109-125">later in this article.</span></span> <span data-ttu-id="73109-126">마이그레이션하려는 경우 [AD RMS에서 Azure Information Protection으로 마이그레이션을 참조 하세요.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)</span><span class="sxs-lookup"><span data-stu-id="73109-126">If you prefer to migrate, see [Migrating from AD RMS to Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)</span></span>

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a><span data-ttu-id="73109-127">AD RMS (Active Directory Rights Management Services)와 함께 Azure Information Protection을 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="73109-127">Can I use Azure Information Protection with Active Directory Rights Management Services (AD RMS)?</span></span>

<span data-ttu-id="73109-128">아니요.</span><span class="sxs-lookup"><span data-stu-id="73109-128">No.</span></span> <span data-ttu-id="73109-129">이 배포 시나리오는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="73109-129">This is not a supported deployment scenario.</span></span> <span data-ttu-id="73109-130">추가 옵트아웃 단계를 수행 하지 않고 일부 컴퓨터가 Azure 권한 관리 서비스를 자동으로 시작 하 고 AD RMS 클러스터에 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73109-130">Without taking the additional opt-out steps, some computers might automatically start using the Azure Rights Management service and also connect to your AD RMS cluster.</span></span> <span data-ttu-id="73109-131">이 시나리오는 지원 되지 않으며 결과를 신뢰할 수 없으므로 다음 30 일 이내에 이러한 변경 내용을 취소 하는 것이 중요 하므로 이러한 새로운 기능을 롤아웃하기는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="73109-131">This scenario isn't supported and has unreliable results, so it's important that you opt out of this change within the next 30 days before we roll out these new features.</span></span> <span data-ttu-id="73109-132">옵트아웃 하는 방법에 대 한 자세한 내용은 "use AD RMS, 옵트아웃 (opt out)"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="73109-132">For information on how to opt-out, see "I use AD RMS, how do I opt out?"</span></span> <span data-ttu-id="73109-133">이 문서의 뒷부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73109-133">later in this article.</span></span> <span data-ttu-id="73109-134">마이그레이션하려는 경우 [AD RMS에서 Azure Information Protection으로 마이그레이션을 참조 하세요.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)</span><span class="sxs-lookup"><span data-stu-id="73109-134">If you prefer to migrate, see [Migrating from AD RMS to Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)</span></span>

## <a name="how-do-i-know-if-im-using-ad-rms"></a><span data-ttu-id="73109-135">AD RMS를 사용 하 고 있는지 여부를 어떻게 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="73109-135">How do I know if I'm using AD RMS?</span></span>

<span data-ttu-id="73109-136">다음 지침에 따라 ad rms [(Active Directory Rights Management Services)를 배포 하는 경우 Azure 권한 관리에 대 한 환경을 준비 하는](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73109-136">Use these instructions from [Preparing the environment for Azure Rights Management when you also have Active Directory Rights Management Services (AD RMS)](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) to check if you have deployed AD RMS:</span></span>

1. <span data-ttu-id="73109-137">선택 사항 이지만 대부분의 AD RMS 배포는 도메인 컴퓨터에서 AD RMS 클러스터를 검색할 수 있도록 SCP (서비스 연결 지점)를 Active Directory에 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="73109-137">Although optional, most AD RMS deployments publish the service connection point (SCP) to Active Directory so that domain computers can discover the AD RMS cluster.</span></span>

<span data-ttu-id="73109-138">ADSI 편집을 사용 하 여 Active Directory에 게시 된 SCP가 있는지 확인: CN = Configuration [server name], CN = Services, CN = RightsManagementServices, CN = SCP</span><span class="sxs-lookup"><span data-stu-id="73109-138">Use ADSI Edit to see whether you have an SCP published in Active Directory: CN=Configuration [server name], CN=Services, CN=RightsManagementServices, CN=SCP</span></span>

2. <span data-ttu-id="73109-139">SCP를 사용 하지 않는 경우 AD RMS 클러스터에 연결 하는 Windows 컴퓨터는 Windows 레지스트리: HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MSIPC\ServiceLocation 또는 HKEY_LOCAL_MACHINE \SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation을 사용 하 여 클라이언트 쪽 서비스 검색 또는 라이선스 리디렉션에 대해 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73109-139">If you are not using an SCP, Windows computers that connect to an AD RMS cluster must be configured for client-side service discovery or licensing redirection by using the Windows registry: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation</span></span>

<span data-ttu-id="73109-140">이러한 레지스트리 구성에 대 한 자세한 내용은 [Windows 레지스트리를 사용 하 여 클라이언트 쪽 서비스 검색 설정](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) 및 [라이선스 서버 트래픽 리디렉션을](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="73109-140">For more information about these registry configurations, see [Enabling client-side service discovery by using the Windows registry](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) and [Redirecting licensing server traffic](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic).</span></span>

## <a name="i-use-ad-rms-how-do-i-opt-out"></a><span data-ttu-id="73109-141">AD RMS를 사용 하는 경우 어떻게 하면이를 옵트아웃 합니까?</span><span class="sxs-lookup"><span data-stu-id="73109-141">I use AD RMS, how do I opt out?</span></span>

<span data-ttu-id="73109-142">예정 된 변경 내용을 취소 하려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="73109-142">To opt out of the upcoming change, complete these steps:</span></span>

1. <span data-ttu-id="73109-143">조직에서 전역 관리자 권한이 있는 회사 또는 학교 계정을 사용 하 여 Windows PowerShell 세션을 시작 하 고 Exchange Online에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="73109-143">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="73109-144">지침을 확인하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="73109-144">For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="73109-145">다음 구문을 사용 하 여 IRMConfiguration cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="73109-145">Run the Set-IRMConfiguration cmdlet using the following syntax:</span></span>

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a><span data-ttu-id="73109-146">이 변경 사항을 적용 한 후에는 무엇을 기대할 것인가?</span><span class="sxs-lookup"><span data-stu-id="73109-146">What can I expect after this change has been made?</span></span>

<span data-ttu-id="73109-147">이 기능이 사용 하도록 설정 된 경우에는 [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) 에서 발표 된 새로운 버전의 Office 365 메시지 암호화를 사용 하 고 Azure Information protection의 암호화 및 보호 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73109-147">Once this is enabled, provided you haven't opted out, you can start using the new version of Office 365 Message Encryption which was announced at [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) and leverages the encryption and protection capabilities of Azure Information Protection.</span></span>

![웹용 Outlook에서 OME protected 메시지를 표시 하는 스크린샷](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

<span data-ttu-id="73109-149">새로운 향상 된 기능에 대 한 자세한 내용은 [Office 365 메시지 암호화](../../compliance/ome.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="73109-149">For more information about the new enhancements, see [Office 365 Message Encryption](../../compliance/ome.md).</span></span>
