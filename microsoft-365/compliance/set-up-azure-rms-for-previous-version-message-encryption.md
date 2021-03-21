---
title: 이전 버전의 메시지 암호화에 대해 Azure 권한 관리 설정
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/30/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 2cba47b3-f09e-4911-9207-ac056fcb9db7
description: 이전 버전의 Office 365 메시지 암호화는 Microsoft Azure 권한 관리(이전의 Active Directory Rights Management)에 Windows Azure 사용합니다.
ms.openlocfilehash: 978a8027c79de574b80aeedabcbbd51fa6f9e2a0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919494"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a><span data-ttu-id="dbd27-103">이전 버전의 메시지 암호화에 대해 Azure 권한 관리 설정</span><span class="sxs-lookup"><span data-stu-id="dbd27-103">Set up Azure Rights Management for the previous version of Message Encryption</span></span>

<span data-ttu-id="dbd27-104">이 항목에서는 이전 버전의 Office 365 OME(메시지 암호화)에서 사용하기 위해 Azure Information Protection의 일부인 RMS(Azure 권한 관리)를 활성화하고 설정하기 위해 따라야 하는 단계에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-104">This topic describes the steps you need to follow in order to activate and then set up Azure Rights Management (RMS), part of Azure Information Protection, for use with the previous version of Office 365 Message Encryption (OME).</span></span>

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a><span data-ttu-id="dbd27-105">이 문서는 이전 버전의 OME에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-105">This article only applies to the previous version of OME</span></span>

<span data-ttu-id="dbd27-106">아직 조직을 새 OME 기능으로 이동하지 않았지만 이미 OME를 배포한 경우 이 문서의 정보가 조직에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-106">If you haven't yet moved your organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization.</span></span> <span data-ttu-id="dbd27-107">조직에 적절한 새 OME 기능으로 이동하는 계획을 세우는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-107">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="dbd27-108">자세한 내용은 [Set up new Office 365 Message Encryption capabilities을 참조하십시오.](set-up-new-message-encryption-capabilities.md)</span><span class="sxs-lookup"><span data-stu-id="dbd27-108">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="dbd27-109">새 기능의 작동 방식에 대한 자세한 내용은 [Office 365 메시지 암호화를 참조하세요.](ome.md)</span><span class="sxs-lookup"><span data-stu-id="dbd27-109">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span> <span data-ttu-id="dbd27-110">이 문서의 나머지부분에서는 새 OME 기능을 릴리스하기 전에 OME 동작을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-110">The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="dbd27-111">이전 버전의 Office 365 메시지 암호화 사용에 대한 선행 준비</span><span class="sxs-lookup"><span data-stu-id="dbd27-111">Prerequisites for using the previous version of Office 365 Message Encryption</span></span>
<span data-ttu-id="dbd27-112"><a name="warmprereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="dbd27-112"><a name="warmprereqs"> </a></span></span>

<span data-ttu-id="dbd27-113">IRM을 포함한 Office 365 메시지 암호화(OME)는 Azure RMS(Azure 권한 관리)에 따라 달라 습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-113">Office 365 Message Encryption (OME), including IRM, depends on Azure Rights Management (Azure RMS).</span></span> <span data-ttu-id="dbd27-114">Azure RMS는 Azure Information Protection에서 사용하는 보호 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-114">Azure RMS is the protection technology used by Azure Information Protection.</span></span> <span data-ttu-id="dbd27-115">OME를 사용하려면 조직에 Azure 권한 관리 구독이 포함된 Exchange Online 또는 Exchange Online Protection 구독이 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-115">To use OME, your organization must include an Exchange Online or Exchange Online Protection subscription that, in turn, includes an Azure Rights Management subscription.</span></span>
  
- <span data-ttu-id="dbd27-116">구독에 포함된 내용에 대한 확신이 없는 경우 메시지 정책, 복구 및 규정 준수에 대한 Exchange Online 서비스 [설명을 참조하세요.](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)</span><span class="sxs-lookup"><span data-stu-id="dbd27-116">If you're not sure of what your subscription includes, see the Exchange Online service descriptions for [Message Policy, Recovery, and Compliance](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span></span>

- <span data-ttu-id="dbd27-117">Azure 권한 관리가 있지만 Exchange Online 또는 Exchange Online Protection에 대해 설정되지 않은 경우 이 문서에서는 Azure 권한 관리를 활성화하는 방법을 설명한 다음 Azure 권한 관리에서 작동할 수 있는 OME를 설정하는 가장 좋은 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-117">If you have Azure Rights Management but it's not set up for Exchange Online or Exchange Online Protection, this article explains how to activate Azure Rights Management and then the describes the best way to set up OME to work with Azure Rights Management.</span></span>

- <span data-ttu-id="dbd27-118">OME를 설정한 방법에 따라 Exchange Online 또는 Exchange Online Protection용 Azure 권한 관리에서 작동 OME를 이미 설정한 경우 OME 및 새 기능을 바로 사용할 준비가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-118">If you've already set up OME to work with Azure Rights Management for Exchange Online or Exchange Online Protection, depending on how you set it up, you may be ready to start using OME and its new capabilities right away.</span></span> <span data-ttu-id="dbd27-119">이 문서에서는 OME를 올바르게 설정해야 하는지, 설정을 변경해야 하는 경우 어떻게 해야 하는지, 설치를 변경하지 않을 경우 어떻게 될지 결정하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-119">This article explains how to determine if you've set OME up correctly, what to do if you need to change your setup, and what happens if you choose not to change your setup.</span></span> <span data-ttu-id="dbd27-120">예를 들어 새 기능을 사용하려면 OME와 함께 Azure RMS를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-120">For example, in order to use the new capabilities, you must use Azure RMS with OME.</span></span> <span data-ttu-id="dbd27-121">새 기능을 프레미스 Active Directory RMS와 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-121">You can't use the new capabilities with an on-premises Active Directory RMS.</span></span>

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a><span data-ttu-id="dbd27-122">Office 365에서 이전 버전의 OME에 대한 Azure 권한 관리 활성화</span><span class="sxs-lookup"><span data-stu-id="dbd27-122">Activate Azure Rights Management for  the previous version of OME in Office 365</span></span>

<span data-ttu-id="dbd27-123">조직의 사용자가 보내는 메시지에 정보 보호를 적용하고 Azure 권한 관리 서비스에서 보호된 메시지와 파일을 열 수 있도록 Azure 권한 관리를 활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-123">You need to activate Azure Rights Management so that the users in your organization can apply information protection to messages that they send, and open messages and files that have been protected by the Azure Rights Management service.</span></span> <span data-ttu-id="dbd27-124">자세한 내용은 Azure 권한 관리 [활성화를 참조하세요.](/azure/information-protection/activate-service)</span><span class="sxs-lookup"><span data-stu-id="dbd27-124">For instructions, see [Activating Azure Rights Management](/azure/information-protection/activate-service).</span></span> <span data-ttu-id="dbd27-125">정품 인증을 완료한 후 여기로 돌아가 이 문서의 작업을 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-125">Once you've completed the activation, return here and continue with the tasks in this article.</span></span>
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a><span data-ttu-id="dbd27-126">신뢰할 수 있는 게시 도메인(TPD)을 가져와서 Azure RMS를 사용할 이전 버전의 OME 설정</span><span class="sxs-lookup"><span data-stu-id="dbd27-126">Set up the previous version of OME to use Azure RMS by importing trusted publishing domains (TPDs)</span></span>

<span data-ttu-id="dbd27-127">TPD는 조직의 권한 관리 설정에 대한 정보를 포함하는 XML 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-127">A TPD is an XML file that contains information about your organization's rights management settings.</span></span> <span data-ttu-id="dbd27-128">예를 들어 TPD에는 인증서 및 라이선스 서명 및 암호화에 사용되는 SLC(서버 라이선스 인증서), 라이선스 및 게시에 사용되는 URL에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-128">For example, the TPD contains information about the server licensor certificate (SLC) used for signing and encrypting certificates and licenses, the URLs used for licensing and publishing, and so on.</span></span> <span data-ttu-id="dbd27-129">조직에 TPD를 가져오는 데 사용할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dbd27-129">You import the TPD into your organization by using Windows PowerShell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="dbd27-130">이전에는 AD RMS(Active Directory Rights Management Service)에서 조직으로 TPD를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-130">Previously, you could choose to import TPDs from the Active Directory Rights Management service (AD RMS) into your organization.</span></span> <span data-ttu-id="dbd27-131">그러나 이렇게 하면 새 OME 기능을 사용할 수 없는 것이 며 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-131">However, doing so will prevent you from using the new OME capabilities and is not recommended.</span></span> <span data-ttu-id="dbd27-132">조직이 현재 이러한 방식으로 구성되어 있는 경우, Microsoft는 사내 Active Directory RMS에서 클라우드 기반 Azure Information Protection으로 마이그레이션할 계획을 만드는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-132">If your organization is currently configured this way, Microsoft recommends that you create a plan to migrate from your on-premises Active Directory RMS to cloud-based Azure Information Protection.</span></span> <span data-ttu-id="dbd27-133">자세한 내용은 [AD RMS에서 Azure Information Protection으로 마이그레이션을 참조하세요.](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)</span><span class="sxs-lookup"><span data-stu-id="dbd27-133">For more information, see [Migrating from AD RMS to Azure Information Protection](/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span></span> <span data-ttu-id="dbd27-134">Azure Information Protection으로의 마이그레이션을 완료해야 새 OME 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-134">You will not be able to use the new OME capabilities until you have completed the migration to Azure Information Protection.</span></span>
  
 <span data-ttu-id="dbd27-135">**Azure RMS에서 TPD를 가져오기 위해**</span><span class="sxs-lookup"><span data-stu-id="dbd27-135">**To import TPDs from Azure RMS**</span></span>
  
1. <span data-ttu-id="dbd27-136">[원격 PowerShell을 사용하여 Exchange Online에 연결합니다.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="dbd27-136">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="dbd27-137">조직의 지리적 위치에 해당하는 키 공유 URL을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="dbd27-137">Choose the key-sharing URL that corresponds to your organization's geographic location:</span></span>

|<span data-ttu-id="dbd27-138">**위치**</span><span class="sxs-lookup"><span data-stu-id="dbd27-138">**Location**</span></span>|<span data-ttu-id="dbd27-139">**키 공유 위치 URL**</span><span class="sxs-lookup"><span data-stu-id="dbd27-139">**Key sharing location URL**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dbd27-140">북미</span><span class="sxs-lookup"><span data-stu-id="dbd27-140">North America</span></span>  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="dbd27-141">유럽 연합</span><span class="sxs-lookup"><span data-stu-id="dbd27-141">European Union</span></span>  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="dbd27-142">아시아</span><span class="sxs-lookup"><span data-stu-id="dbd27-142">Asia</span></span>  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="dbd27-143">남미</span><span class="sxs-lookup"><span data-stu-id="dbd27-143">South America</span></span>  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="dbd27-144">Office 365 Government(정부 커뮤니티 클라우드)</span><span class="sxs-lookup"><span data-stu-id="dbd27-144">Office 365 for Government (Government Community Cloud)</span></span>  <br/> <span data-ttu-id="dbd27-145">이 RMS 키 공유 위치는 Government SKUS용 Office 365를 구입한 고객을 위해 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-145">This RMS key-sharing location is reserved for customers who have purchased Office 365 for Government SKUs.</span></span>  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. <span data-ttu-id="dbd27-146">다음과 같이 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet을 실행하여 키 공유 위치를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-146">Configure the key-sharing location by running the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows:</span></span> 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   <span data-ttu-id="dbd27-147">예를 들어 조직이 북미에 있는 경우 키 공유 위치를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-147">For example, to configure the key sharing location if your organization is located in North America:</span></span>

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. <span data-ttu-id="dbd27-148">-RMSOnline 스위치를 사용하여 [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) cmdlet을 실행하여 Azure 권한 관리에서 TPD를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-148">Run the [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain) cmdlet with the -RMSOnline switch to import the TPD from Azure Rights Management:</span></span> 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   <span data-ttu-id="dbd27-149">여기서  *TPDName은*  TPD에 사용할 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-149">Where  *TPDName*  is the name you want to use for the TPD.</span></span> <span data-ttu-id="dbd27-150">예를 들면 "Contoso North American TPD"입니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-150">For example, "Contoso North American TPD".</span></span> 

5. <span data-ttu-id="dbd27-151">Azure 권한 관리 서비스를 사용하도록 조직을 성공적으로 구성한 경우 다음과 같이 -RMSOnline 스위치를 사용하여 [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-151">To verify that you successfully configured your organization to use the Azure Rights Management service, run the [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration) cmdlet with the -RMSOnline switch as follows:</span></span>

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   <span data-ttu-id="dbd27-152">무엇보다 이 cmdlet은 Azure 권한 관리 서비스에 대한 연결을 확인하고 TPD를 다운로드하고 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-152">Among other things, this cmdlet checks connectivity with the Azure Rights Management service, downloads the TPD, and checks its validity.</span></span>

6. <span data-ttu-id="dbd27-153">다음과 같이 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet을 실행하여 웹용 Outlook 및 Outlook에서 Azure 권한 관리 템플릿을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-153">Run the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows to disable Azure Rights Management templates from being available in Outlook on the web and Outlook:</span></span> 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. <span data-ttu-id="dbd27-154">다음과 같이 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet을 실행하여 클라우드 기반 전자 메일 조직에 대해 Azure 권한 관리를 사용하도록 설정하고 Office 365 메시지 암호화에 대해 Azure 권한 관리를 사용하도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-154">Run the [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration) cmdlet as follows to enable Azure Rights Management for your cloud-based email organization and configure it to use Azure Rights Management for Office 365 Message Encryption:</span></span>

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. <span data-ttu-id="dbd27-155">TPD를 가져와 Azure 권한 관리를 사용하도록 설정한지 확인을 위해 Test-IRMConfiguration cmdlet을 사용하여 Azure 권한 관리 기능을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-155">To verify that you have successfully imported the TPD and enabled Azure Rights Management, use the Test-IRMConfiguration cmdlet to test Azure Rights Management functionality.</span></span> <span data-ttu-id="dbd27-156">자세한 내용은 [Test-IRMConfiguration의](/powershell/module/exchange/test-irmconfiguration)"예제 1"을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-156">For details, see "Example 1" in [Test-IRMConfiguration](/powershell/module/exchange/test-irmconfiguration).</span></span>

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a><span data-ttu-id="dbd27-157">Azure Information Protection이 아닌 Active Directory 권한 관리로 이전 버전의 OME를 설정했습니다. 어떻게 해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="dbd27-157">I have the previous version of OME set up with Active Directory Rights Management not Azure Information Protection, what do I do?</span></span>
<span data-ttu-id="dbd27-158"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="dbd27-158"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="dbd27-159">Active Directory Rights Management를 사용하여 기존 Office 365 메시지 암호화 메일 흐름 규칙을 계속 사용할 수 있지만 새 OME 기능을 구성하거나 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-159">You can continue to use your existing Office 365 Message Encryption mail flow rules with Active Directory Rights Management, but you can't configure or use the new OME capabilities.</span></span> <span data-ttu-id="dbd27-160">대신 Azure Information Protection으로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbd27-160">Instead, you need to migrate to Azure Information Protection.</span></span> <span data-ttu-id="dbd27-161">마이그레이션 및 조직의 의미에 대한 자세한 내용은 [Ad RMS에서 Azure Information Protection으로 마이그레이션을 참조하세요.](/information-protection/deploy-use/prepare-environment-adrms)</span><span class="sxs-lookup"><span data-stu-id="dbd27-161">For information about migration and what this means for your organization, see [Migrating from AD RMS to Azure Information Protection](/information-protection/deploy-use/prepare-environment-adrms).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="dbd27-162">다음 단계</span><span class="sxs-lookup"><span data-stu-id="dbd27-162">Next steps</span></span>
<span data-ttu-id="dbd27-163"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="dbd27-163"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="dbd27-164">Azure 권한 관리 설정을 완료한 후 새 OME 기능을 사용하도록 설정하려면 Azure Information Protection을 토대하여 구축된 [새 Office 365](./set-up-new-message-encryption-capabilities.md) 메시지 암호화 기능 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dbd27-164">Once you've completed Azure Rights Management setup, if you want to enable the new OME capabilities, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](./set-up-new-message-encryption-capabilities.md)</span></span>
  
<span data-ttu-id="dbd27-165">조직에서 새 OME 기능을 사용할 수 있도록 설정한 후 새 OME 기능으로 전자 메일 메시지를 보호하는 메일 흐름 규칙 [정의를 사용할 준비가 된 것입니다.](define-mail-flow-rules-to-encrypt-email.md)</span><span class="sxs-lookup"><span data-stu-id="dbd27-165">After you've set up your organization to use the new OME capabilities, you're ready to [Define mail flow rules to protect email messages with new OME capabilities](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="dbd27-166">관련 항목</span><span class="sxs-lookup"><span data-stu-id="dbd27-166">Related topics</span></span>
<span data-ttu-id="dbd27-167"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="dbd27-167"><a name="importTPDs"> </a></span></span>

[<span data-ttu-id="dbd27-168">Office 365의 암호화</span><span class="sxs-lookup"><span data-stu-id="dbd27-168">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="dbd27-169">Office 365의 암호화에 대한 기술 관련 세부 정보</span><span class="sxs-lookup"><span data-stu-id="dbd27-169">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="dbd27-170">Azure 권한 관리란?</span><span class="sxs-lookup"><span data-stu-id="dbd27-170">What is Azure Rights Management?</span></span>](/information-protection/understand-explore/what-is-azure-rms)