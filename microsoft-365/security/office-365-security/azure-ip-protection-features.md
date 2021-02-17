---
title: 기존 테넌트에 롤아웃된 Azure Information Protection의 보호 기능
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 7ad6f58e-65d7-4c82-8e65-0b773666634d
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 Azure Information Protection의 보호 기능에 롤아웃되는 변경 내용에 대해 설명합니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 0769306c3aa2d1a357e1d5999d1a1406c02aa5f3
ms.sourcegitcommit: a9ac702c9efc9defded3bfa65618b94bac00c237
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/16/2021
ms.locfileid: "50261564"
---
# <a name="protection-features-in-azure-information-protection-rolling-out-to-existing-tenants"></a><span data-ttu-id="eac45-103">기존 테넌트에 롤아웃된 Azure Information Protection의 보호 기능</span><span class="sxs-lookup"><span data-stu-id="eac45-103">Protection features in Azure Information Protection rolling out to existing tenants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="eac45-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="eac45-104">**Applies to**</span></span>
- [<span data-ttu-id="eac45-105">Office 365용 Microsoft Defender 플랜 2</span><span class="sxs-lookup"><span data-stu-id="eac45-105">Microsoft Defender for Office 365 plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="eac45-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eac45-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="eac45-107">정보 보호의 초기 단계를 지원하기 위해 2018년 7월부터 모든 Azure Information Protection 적격 테넌트에는 기본적으로 Azure Information Protection의 보호 기능이 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-107">To help with the initial step in protecting your information, starting July 2018 all Azure Information Protection eligible tenants will have the protection features in Azure Information Protection turned on by default.</span></span> <span data-ttu-id="eac45-108">Azure Information Protection의 보호 기능은 이전 Office 365에서 권한 관리 또는 Azure RMS로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-108">The protection features in Azure Information Protection were formerly known in Office 365 as Rights Management or Azure RMS.</span></span> <span data-ttu-id="eac45-109">조직에 Office E3 서비스 플랜 또는 상위 서비스 플랜이 있는 경우 이러한 기능을 롤아웃할 때 Azure Information Protection을 통해 정보를 보호하기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-109">If your organization has an Office E3 service plan or a higher service plan you will now get a head start protecting information through Azure Information Protection when we roll out these features.</span></span>

## <a name="changes-beginning-july-1-2018"></a><span data-ttu-id="eac45-110">2018년 7월 1일 이후 변경 내용</span><span class="sxs-lookup"><span data-stu-id="eac45-110">Changes beginning July 1, 2018</span></span>

<span data-ttu-id="eac45-111">2018년 7월 1일부터 Microsoft는 다음 구독 계획 중 하나를 사용하여 모든 조직에 대해 Azure Information Protection의 보호 기능을 사용하도록 설정할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-111">Starting July 1, 2018, Microsoft will enable the protection capability in Azure Information Protection for all organizations with one of the following subscription plans:</span></span>

- <span data-ttu-id="eac45-112">Office 365 메시지 암호화는 Office 365 E3 및 E5, Microsoft E3 및 E5, Office 365 A1, A3 및 A5 및 Office 365 G3 및 G5의 일부로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-112">Office 365 Message Encryption is offered as part of Office 365 E3 and E5, Microsoft E3 and E5, Office 365 A1, A3, and A5, and Office 365 G3 and G5.</span></span> <span data-ttu-id="eac45-113">Azure Information Protection의 새로운 보호 기능을 받기 위해 추가 라이선스가 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-113">You do not need additional licenses to receive the new protection capabilities powered by Azure Information Protection.</span></span>

- <span data-ttu-id="eac45-114">또한 Azure Information Protection 계획 1을 다음 계획에 추가하여 새로운 Office 365 메시지 암호화 기능을 받을 수 있습니다. Exchange Online 계획 1, Exchange Online 계획 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard 또는 Office 365 Enterprise E1.</span><span class="sxs-lookup"><span data-stu-id="eac45-114">You can also add Azure Information Protection Plan 1 to the following plans to receive the new Office 365 Message Encryption capabilities: Exchange Online Plan 1, Exchange Online Plan 2, Office 365 F1, Microsoft 365 Business Basic, Microsoft 365 Business Standard, or Office 365 Enterprise E1.</span></span>

- <span data-ttu-id="eac45-115">Office 365 메시지 암호화를 통해 혜택을 받을 수 있는 각 사용자는 이 기능을 사용할 수 있도록 라이선스가 부여되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-115">Each user benefiting from Office 365 Message Encryption needs to be licensed to be covered by the feature.</span></span>

- <span data-ttu-id="eac45-116">전체 목록은 Office 365 [메시지 암호화에](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) 대한 Exchange Online 서비스 설명을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eac45-116">For the full list, see the [Exchange Online service descriptions](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) for Office 365 Message Encryption.</span></span>

<span data-ttu-id="eac45-117">테넌트 관리자는 Office 365 관리자 포털에서 보호 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-117">Tenant administrators can check the protection status in the Office 365 administrator portal.</span></span>

![Screenshot that shows that rights management in Office 365 is activated.](../../media/303453c8-e4a5-4875-b49f-e80c3eb7b91e.png)

## <a name="why-are-we-making-this-change"></a><span data-ttu-id="eac45-119">이러한 변경을 하는 이유는 무엇일까요?</span><span class="sxs-lookup"><span data-stu-id="eac45-119">Why are we making this change?</span></span>

<span data-ttu-id="eac45-120">Office 365 메시지 암호화는 Azure Information Protection의 보호 기능을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-120">Office 365 Message Encryption leverages the protection capabilities in Azure Information Protection.</span></span> <span data-ttu-id="eac45-121">Microsoft 365의 정보 보호에 대한 최근 개선된 기능과 Microsoft 365의 정보 보호에 대한 광범위한 투자의 핵심은 지금까지 암호화 기술을 설정하기 어려웠기 때문에 조직이 보다 쉽게 보호 기능을 켜고 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-121">At the heart of the recent improvements to Office 365 Message Encryption and our broader investments to information protection in Microsoft 365, we are making it easier for organizations to turn on and use our protection capabilities, as historically, encryption technologies have been difficult to set up.</span></span> <span data-ttu-id="eac45-122">기본적으로 Azure Information Protection의 보호 기능을 켜면 중요한 데이터를 신속하게 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-122">By turning on the protection features in Azure Information Protection by default, you can quickly get started to protect your sensitive data.</span></span>

## <a name="does-this-impact-me"></a><span data-ttu-id="eac45-123">이 영향이 내게 영향을 미치나요?</span><span class="sxs-lookup"><span data-stu-id="eac45-123">Does this impact me?</span></span>

<span data-ttu-id="eac45-124">조직에서 적합한 Office 365 라이선스를 구입한 경우 테넌트는 이 변경의 영향을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-124">If your organization has purchased an eligible Office 365 license, then your tenant will be impacted by this change.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eac45-125">프레미스 환경에서 AD RMS(Active Directory Rights Management Services)를 사용하는 경우 다음 30일 이내에 이 변경을 롤아웃하기 전에 이 변경을 즉시 옵트아웃하거나 Azure Information Protection으로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-125">If you're using Active Directory Rights Management Services (AD RMS) in your on-premises environment, you must either opt-out of this change immediately or migrate to Azure Information Protection before we roll out this change within the next 30 days.</span></span> <span data-ttu-id="eac45-126">옵트아웃하는 방법에 대한 자세한 내용은 "AD RMS를 사용하세요. 옵트아웃하는 방법"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eac45-126">For information on how to opt-out, see "I use AD RMS, how do I opt out?"</span></span> <span data-ttu-id="eac45-127">후반부에 이 문서의</span><span class="sxs-lookup"><span data-stu-id="eac45-127">later in this article.</span></span> <span data-ttu-id="eac45-128">마이그레이션하려면 [AD RMS에서 Azure Information Protection으로 마이그레이션을 참조하세요.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)</span><span class="sxs-lookup"><span data-stu-id="eac45-128">If you prefer to migrate, see [Migrating from AD RMS to Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span></span>

## <a name="can-i-use-azure-information-protection-with-active-directory-rights-management-services-ad-rms"></a><span data-ttu-id="eac45-129">AD RMS(Azure Information Protection)Active Directory Rights Management Services 사용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="eac45-129">Can I use Azure Information Protection with Active Directory Rights Management Services (AD RMS)?</span></span>

<span data-ttu-id="eac45-130">아니요.</span><span class="sxs-lookup"><span data-stu-id="eac45-130">No.</span></span> <span data-ttu-id="eac45-131">이는 지원되는 배포 시나리오가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-131">This is not a supported deployment scenario.</span></span> <span data-ttu-id="eac45-132">추가 옵트아웃 단계를 수행하지 않으면 일부 컴퓨터에서 Azure 권한 관리 서비스를 자동으로 시작하고 AD RMS 클러스터에 연결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-132">Without taking the additional opt-out steps, some computers might automatically start using the Azure Rights Management service and also connect to your AD RMS cluster.</span></span> <span data-ttu-id="eac45-133">이 시나리오는 지원되지 않는 것이고 신뢰할 수 없는 결과가 있으므로 이러한 새 기능을 롤아웃하기 전에 다음 30일 이내에 이 변경을 옵트아웃(opt out)하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-133">This scenario isn't supported and has unreliable results, so it's important that you opt out of this change within the next 30 days before we roll out these new features.</span></span> <span data-ttu-id="eac45-134">옵트아웃하는 방법에 대한 자세한 내용은 "AD RMS를 사용하세요. 옵트아웃하는 방법"을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eac45-134">For information on how to opt-out, see "I use AD RMS, how do I opt out?"</span></span> <span data-ttu-id="eac45-135">후반부에 이 문서의</span><span class="sxs-lookup"><span data-stu-id="eac45-135">later in this article.</span></span> <span data-ttu-id="eac45-136">마이그레이션을 원하는 경우 [AD RMS에서 Azure Information Protection으로 마이그레이션을 참조하세요.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)</span><span class="sxs-lookup"><span data-stu-id="eac45-136">If you prefer to migrate, see [Migrating from AD RMS to Azure Information Protection.](https://docs.microsoft.com/azure/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)</span></span>

## <a name="how-do-i-know-if-im-using-ad-rms"></a><span data-ttu-id="eac45-137">AD RMS를 사용하는지 어떻게 알 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="eac45-137">How do I know if I'm using AD RMS?</span></span>

<span data-ttu-id="eac45-138">AD RMS(Active Directory Rights Management Services)도 있는 경우 Azure 권한 관리를 위한 환경 준비에서 다음 지침을 사용하여 AD [RMS를](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) 배포한지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-138">Use these instructions from [Preparing the environment for Azure Rights Management when you also have Active Directory Rights Management Services (AD RMS)](https://docs.microsoft.com/azure/information-protection/deploy-use/prepare-environment-adrms) to check if you have deployed AD RMS:</span></span>

1. <span data-ttu-id="eac45-139">선택 사항이지만 대부분의 AD RMS 배포는 도메인 컴퓨터가 AD RMS 클러스터를 검색할 수 있도록 SCP(서비스 연결 지점)를 Active Directory에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-139">Although optional, most AD RMS deployments publish the service connection point (SCP) to Active Directory so that domain computers can discover the AD RMS cluster.</span></span>

   <span data-ttu-id="eac45-140">ADSI 편집을 사용하여 SCP가 Active Directory에 게시되어 있는지 확인합니다. CN=Configuration [서버 이름], CN=Services, CN=RightsManagementServices, CN=SCP</span><span class="sxs-lookup"><span data-stu-id="eac45-140">Use ADSI Edit to see whether you have an SCP published in Active Directory: CN=Configuration [server name], CN=Services, CN=RightsManagementServices, CN=SCP</span></span>

2. <span data-ttu-id="eac45-141">SCP를 사용하지 않는 경우 WINDOWS 레지스트리를 사용하여 AD RMS 클러스터에 연결하는 Windows 컴퓨터를 클라이언트 쪽 서비스 검색 또는 라이선스 리디렉션에 맞게 구성해야 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation` 합니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-141">If you are not using an SCP, Windows computers that connect to an AD RMS cluster must be configured for client-side service discovery or licensing redirection by using the Windows registry: `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\ServiceLocation or HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\MSIPC\ServiceLocation`.</span></span>

<span data-ttu-id="eac45-142">이러한 레지스트리 구성에 대한 자세한 내용은 [Windows](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) 레지스트리를 사용하여 클라이언트 쪽 서비스 검색 사용 및 라이선스 서버 트래픽 리디렉션을 [참조하세요.](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic)</span><span class="sxs-lookup"><span data-stu-id="eac45-142">For more information about these registry configurations, see [Enabling client-side service discovery by using the Windows registry](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#enabling-client-side-service-discovery-by-using-the-windows-registry) and [Redirecting licensing server traffic](https://docs.microsoft.com/azure/information-protection/rms-client/client-deployment-notes#redirecting-licensing-server-traffic).</span></span>

## <a name="i-use-ad-rms-how-do-i-opt-out"></a><span data-ttu-id="eac45-143">AD RMS를 사용, 옵트아웃하는 방법</span><span class="sxs-lookup"><span data-stu-id="eac45-143">I use AD RMS, how do I opt out?</span></span>

<span data-ttu-id="eac45-144">예정된 변경을 옵트아웃(opt out)으로 설정하기 위해 다음 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-144">To opt out of the upcoming change, complete these steps:</span></span>

1. <span data-ttu-id="eac45-145">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 Exchange Online에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-145">Using a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="eac45-146">지침을 확인하려면 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eac45-146">For instructions, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="eac45-147">다음 구문을 Set-IRMConfiguration cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-147">Run the Set-IRMConfiguration cmdlet using the following syntax:</span></span>

  ```powershell
  Set-IRMConfiguration -AutomaticServiceUpdateEnabled $false
  ```

## <a name="what-can-i-expect-after-this-change-has-been-made"></a><span data-ttu-id="eac45-148">이 변경이 만들어진 후 예상할 수 있는 상황</span><span class="sxs-lookup"><span data-stu-id="eac45-148">What can I expect after this change has been made?</span></span>

<span data-ttu-id="eac45-149">이 기능을 사용하도록 설정한 후 옵트아웃하지 않은 경우 [Microsoft Ignite 2017에서](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) 발표된 새로운 버전의 Office 365 메시지 암호화를 사용하여 Azure Information Protection의 암호화 및 보호 기능을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eac45-149">Once this is enabled, provided you haven't opted out, you can start using the new version of Office 365 Message Encryption which was announced at [Microsoft Ignite 2017](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Email-Encryption-and-Rights-Protection/ba-p/110801) and leverages the encryption and protection capabilities of Azure Information Protection.</span></span>

![Screenshot that shows an OME protected message in Outlook on the web.](../../media/599ca9e7-c05a-429e-ae8d-359f1291a3d8.png)

<span data-ttu-id="eac45-151">새로운 기능 향상에 대한 자세한 내용은 [Office 365 메시지 암호화를 참조하세요.](../../compliance/ome.md)</span><span class="sxs-lookup"><span data-stu-id="eac45-151">For more information about the new enhancements, see [Office 365 Message Encryption](../../compliance/ome.md).</span></span>
