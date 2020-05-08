---
title: 이전 버전의 메시지 암호화에 대 한 Azure 권한 관리 설정
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
description: 이전 버전의 Office 365 메시지 암호화는 Microsoft Azure 권한 관리 (이전에는 Windows Azure Active Directory Rights Management)에 따라 달라 집니다.
ms.openlocfilehash: 879f4ec1db8a8cfe1fe3c8d3b1dd9e1fc68dd687
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165919"
---
# <a name="set-up-azure-rights-management-for-the-previous-version-of-message-encryption"></a><span data-ttu-id="22f35-103">이전 버전의 메시지 암호화에 대 한 Azure 권한 관리 설정</span><span class="sxs-lookup"><span data-stu-id="22f35-103">Set up Azure Rights Management for the previous version of Message Encryption</span></span>

<span data-ttu-id="22f35-104">이 항목에서는 이전 버전의 Office 365 메시지 암호화 (OME)에 사용 하기 위해 RMS (Azure 권한 관리), Azure Information Protection의 일부를 설정 하기 위해 수행 해야 하는 단계에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-104">This topic describes the steps you need to follow in order to activate and then set up Azure Rights Management (RMS), part of Azure Information Protection, for use with the previous version of Office 365 Message Encryption (OME).</span></span>

## <a name="this-article-only-applies-to-the-previous-version-of-ome"></a><span data-ttu-id="22f35-105">이 문서는 이전 버전의 OME에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-105">This article only applies to the previous version of OME</span></span>

<span data-ttu-id="22f35-106">아직 조직을 새 OME 기능으로 이동 하지 않았지만 이미 OME을 배포한 경우이 문서의 정보가 조직에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-106">If you haven't yet moved your organization to the new OME capabilities, but you have already deployed OME, then the information in this article applies to your organization.</span></span> <span data-ttu-id="22f35-107">조직에 적합 한 시기에 새 OME 기능으로 바로 이동 하는 계획을 수립 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-107">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="22f35-108">자세한 내용은 [Office 365 메시지 암호화 기능 새로 만들기](set-up-new-message-encryption-capabilities.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22f35-108">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="22f35-109">새 기능이 먼저 작동 하는 방식에 대해 자세히 알아보려면 [Office 365 메시지 암호화](ome.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22f35-109">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span> <span data-ttu-id="22f35-110">이 문서의 나머지 부분에서는 새 OME 기능이 출시 되기 전에 발생 하는 OME 동작을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-110">The rest of this article refers to OME behavior before the release of the new OME capabilities.</span></span>

## <a name="prerequisites-for-using-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="22f35-111">이전 버전의 Office 365 메시지 암호화를 사용 하기 위한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="22f35-111">Prerequisites for using the previous version of Office 365 Message Encryption</span></span>
<span data-ttu-id="22f35-112"><a name="warmprereqs"> </a></span><span class="sxs-lookup"><span data-stu-id="22f35-112"><a name="warmprereqs"> </a></span></span>

<span data-ttu-id="22f35-113">IRM을 포함 하는 Office 365 메시지 암호화 (OME)는 azure RMS (보안 권한 관리)에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-113">Office 365 Message Encryption (OME), including IRM, depends on Azure Rights Management (Azure RMS).</span></span> <span data-ttu-id="22f35-114">Azure RMS는 Azure Information Protection에서 사용 되는 보호 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-114">Azure RMS is the protection technology used by Azure Information Protection.</span></span> <span data-ttu-id="22f35-115">OME를 사용 하려면 조직에서 Azure 권한 관리 구독을 포함 하는 Exchange Online 또는 Exchange Online Protection 구독을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-115">To use OME, your organization must include an Exchange Online or Exchange Online Protection subscription that, in turn, includes an Azure Rights Management subscription.</span></span>
  
- <span data-ttu-id="22f35-116">구독에 포함 된 내용을 모르는 경우 Exchange Online 서비스 설명에서 [메시지 정책, 복구 및 규정 준수](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22f35-116">If you're not sure of what your subscription includes, see the Exchange Online service descriptions for [Message Policy, Recovery, and Compliance](https://technet.microsoft.com/library/exchange-online-message-policy-recovery-and-compliance.aspx).</span></span>

- <span data-ttu-id="22f35-117">Azure 권한 관리가 있지만 Exchange Online 또는 Exchange Online Protection에 대해 설정 되어 있지 않은 경우이 문서에서는 azure 권한 관리를 활성화 하는 방법에 대해 설명 하 고 Azure 권한 관리와 함께 작동 하도록 OME을 설정 하는 가장 효율적인 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-117">If you have Azure Rights Management but it's not set up for Exchange Online or Exchange Online Protection, this article explains how to activate Azure Rights Management and then the describes the best way to set up OME to work with Azure Rights Management.</span></span>

- <span data-ttu-id="22f35-118">Exchange Online 또는 Exchange Online Protection에 대해 Azure Rights Management를 사용 하도록 OME을 이미 설정한 경우이를 설정 하는 방법에 따라 OME 및 새 기능 바로 사용을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-118">If you've already set up OME to work with Azure Rights Management for Exchange Online or Exchange Online Protection, depending on how you set it up, you may be ready to start using OME and its new capabilities right away.</span></span> <span data-ttu-id="22f35-119">이 문서에서는 OME을 올바르게 설정 했는지 여부를 확인 하는 방법, 설치를 변경 해야 하는 경우 수행할 작업 및 설정을 변경 하지 않도록 선택한 경우 수행 되는 작업에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-119">This article explains how to determine if you've set OME up correctly, what to do if you need to change your setup, and what happens if you choose not to change your setup.</span></span> <span data-ttu-id="22f35-120">예를 들어 새 기능을 사용 하려면 OME에서 Azure RMS를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-120">For example, in order to use the new capabilities, you must use Azure RMS with OME.</span></span> <span data-ttu-id="22f35-121">온-프레미스 Active Directory RMS에서는 새 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-121">You can't use the new capabilities with an on-premises Active Directory RMS.</span></span>

## <a name="activate-azure-rights-management-for--the-previous-version-of-ome-in-office-365"></a><span data-ttu-id="22f35-122">Office 365에서 이전 버전의 OME에 대 한 Azure 권한 관리를 활성화 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-122">Activate Azure Rights Management for  the previous version of OME in Office 365</span></span>

<span data-ttu-id="22f35-123">조직의 사용자가 보내는 메시지에 정보 보호를 적용 하 고 Azure 권한 관리 서비스를 통해 보호 된 메시지 및 파일을 여는 경우 Azure 권한 관리를 활성화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-123">You need to activate Azure Rights Management so that the users in your organization can apply information protection to messages that they send, and open messages and files that have been protected by the Azure Rights Management service.</span></span> <span data-ttu-id="22f35-124">자세한 내용은 [Azure 권한 관리 활성화](https://go.microsoft.com/fwlink/p/?LinkId=525775)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22f35-124">For instructions, see [Activating Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=525775).</span></span> <span data-ttu-id="22f35-125">정품 인증을 완료 한 후 여기로 돌아와서이 문서의 작업을 계속 진행 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-125">Once you've completed the activation, return here and continue with the tasks in this article.</span></span>
  
## <a name="set-up-the-previous-version-of-ome-to-use-azure-rms-by-importing-trusted-publishing-domains-tpds"></a><span data-ttu-id="22f35-126">TPDs (트러스트 된 게시 도메인)를 가져와서 Azure RMS를 사용 하도록 OME의 이전 버전을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-126">Set up the previous version of OME to use Azure RMS by importing trusted publishing domains (TPDs)</span></span>

<span data-ttu-id="22f35-127">TPD는 조직의 권한 관리 설정에 대 한 정보가 포함 된 XML 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-127">A TPD is an XML file that contains information about your organization's rights management settings.</span></span> <span data-ttu-id="22f35-128">예를 들어 TPD에는 인증서 및 라이선스 서명 및 암호화에 사용 되는 SLC (서버 사용 허가자 인증서), 라이선스 및 게시에 사용 되는 Url 등이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-128">For example, the TPD contains information about the server licensor certificate (SLC) used for signing and encrypting certificates and licenses, the URLs used for licensing and publishing, and so on.</span></span> <span data-ttu-id="22f35-129">Windows PowerShell을 사용 하 여 조직으로 TPD를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-129">You import the TPD into your organization by using Windows PowerShell.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="22f35-130">이전에는 AD RMS (Active Directory Rights Management service)에서 조직으로 TPDs를 가져오도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-130">Previously, you could choose to import TPDs from the Active Directory Rights Management service (AD RMS) into your organization.</span></span> <span data-ttu-id="22f35-131">그러나 이렇게 하면 새 OME 기능을 사용할 수 없으며 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-131">However, doing so will prevent you from using the new OME capabilities and is not recommended.</span></span> <span data-ttu-id="22f35-132">조직이 현재이 방식으로 구성 된 경우 온-프레미스 Active Directory RMS에서 클라우드 기반 Azure 정보 보호로 마이그레이션하는 계획을 세우는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-132">If your organization is currently configured this way, Microsoft recommends that you create a plan to migrate from your on-premises Active Directory RMS to cloud-based Azure Information Protection.</span></span> <span data-ttu-id="22f35-133">자세한 내용은 [AD RMS에서 Azure Information Protection으로 마이그레이션을](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22f35-133">For more information, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/plan-design/migrate-from-ad-rms-to-azure-rms).</span></span> <span data-ttu-id="22f35-134">Azure Information Protection으로의 마이그레이션을 완료 해야 새 OME 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-134">You will not be able to use the new OME capabilities until you have completed the migration to Azure Information Protection.</span></span>
  
 <span data-ttu-id="22f35-135">**Azure RMS에서 TPDs를 가져오려면**</span><span class="sxs-lookup"><span data-stu-id="22f35-135">**To import TPDs from Azure RMS**</span></span>
  
1. <span data-ttu-id="22f35-136">[원격 PowerShell을 사용 하 여 Exchange Online에 연결](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-136">[Connect to Exchange Online Using Remote PowerShell](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx).</span></span>

2. <span data-ttu-id="22f35-137">조직의 지리적 위치에 해당 하는 키 공유 URL을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-137">Choose the key-sharing URL that corresponds to your organization's geographic location:</span></span>

|<span data-ttu-id="22f35-138">**위치**</span><span class="sxs-lookup"><span data-stu-id="22f35-138">**Location**</span></span>|<span data-ttu-id="22f35-139">**키 공유 위치 URL**</span><span class="sxs-lookup"><span data-stu-id="22f35-139">**Key sharing location URL**</span></span>|
|:-----|:-----|
|<span data-ttu-id="22f35-140">북미</span><span class="sxs-lookup"><span data-stu-id="22f35-140">North America</span></span>  <br/> |https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="22f35-141">유럽 연합</span><span class="sxs-lookup"><span data-stu-id="22f35-141">European Union</span></span>  <br/> |https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="22f35-142">아시아</span><span class="sxs-lookup"><span data-stu-id="22f35-142">Asia</span></span>  <br/> |https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="22f35-143">남미</span><span class="sxs-lookup"><span data-stu-id="22f35-143">South America</span></span>  <br/> |https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
|<span data-ttu-id="22f35-144">Office 365 Government(정부 커뮤니티 클라우드)</span><span class="sxs-lookup"><span data-stu-id="22f35-144">Office 365 for Government (Government Community Cloud)</span></span>  <br/> <span data-ttu-id="22f35-145">이 RMS 키 공유 위치는 정부 Sku 용 Office 365을 구입한 고객을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-145">This RMS key-sharing location is reserved for customers who have purchased Office 365 for Government SKUs.</span></span>  <br/> |https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc  <br/> |
  
3. <span data-ttu-id="22f35-146">다음과 같이 [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) cmdlet을 실행 하 여 키 공유 위치를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-146">Configure the key-sharing location by running the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.160%29.aspx) cmdlet as follows:</span></span> 

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "<RMSKeySharingURL >"
   ```
  
   <span data-ttu-id="22f35-147">예를 들어 조직이 북미에 있는 경우 키 공유 위치를 구성 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-147">For example, to configure the key sharing location if your organization is located in North America:</span></span>

   ```powershell
   Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
   ```

4. <span data-ttu-id="22f35-148">-RMSOnline 스위치를 사용 하 여 [import-rmstrustedpublishingdomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) cmdlet을 실행 하 여 Azure 권한 관리에서 TPD를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-148">Run the [Import-RMSTrustedPublishingDomain](https://technet.microsoft.com/library/jj200724%28v=exchg.150%29.aspx) cmdlet with the -RMSOnline switch to import the TPD from Azure Rights Management:</span></span> 

   ```powershell
   Import-RMSTrustedPublishingDomain -RMSOnline -Name "<TPDName> "
   ```

   <span data-ttu-id="22f35-149">여기서 *T사용자 이름은* TPD에 사용할 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-149">Where  *TPDName*  is the name you want to use for the TPD.</span></span> <span data-ttu-id="22f35-150">예를 들어 "Contoso 북미 미국식 TPD"을 사용할 때</span><span class="sxs-lookup"><span data-stu-id="22f35-150">For example, "Contoso North American TPD".</span></span> 

5. <span data-ttu-id="22f35-151">Azure 권한 관리 서비스를 사용 하도록 조직을 성공적으로 구성 했는지 확인 하려면 다음과 같이-RMSOnline 스위치를 통해 [테스트-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-151">To verify that you successfully configured your organization to use the Azure Rights Management service, run the [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.160%29.aspx) cmdlet with the -RMSOnline switch as follows:</span></span>

   ```powershell
   Test-IRMConfiguration -RMSOnline
   ```

   <span data-ttu-id="22f35-152">무엇 보다도이 cmdlet은 Azure 권한 관리 서비스와의 연결을 확인 하 고, TPD를 다운로드 하 고, 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-152">Among other things, this cmdlet checks connectivity with the Azure Rights Management service, downloads the TPD, and checks its validity.</span></span>

6. <span data-ttu-id="22f35-153">다음과 같이 [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet을 실행 하 여 웹 및 Outlook에서 Outlook에서 Azure 권한 관리 템플릿을 사용할 수 없도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-153">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to disable Azure Rights Management templates from being available in Outlook on the web and Outlook:</span></span> 

   ```powershell
   Set-IRMConfiguration -ClientAccessServerEnabled $false
   ```

7. <span data-ttu-id="22f35-154">클라우드 기반 전자 메일 조직에 대해 Azure 권한 관리를 사용 하도록 설정 하 고 Office 365 메시지 암호화에 대해 Azure 권한 관리를 사용 하도록 configure [-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-154">Run the [Set-IRMConfiguration](https://technet.microsoft.com/library/dd979792%28v=exchg.150%29.aspx) cmdlet as follows to enable Azure Rights Management for your cloud-based email organization and configure it to use Azure Rights Management for Office 365 Message Encryption:</span></span>

   ```powershell
   Set-IRMConfiguration -InternalLicensingEnabled $true
   ```

8. <span data-ttu-id="22f35-155">TPD를 올바르게 가져왔는지 Azure 권한 관리를 사용 하도록 설정 했는지 확인 하려면 IRMConfiguration cmdlet을 사용 하 여 Azure 권한 관리 기능을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-155">To verify that you have successfully imported the TPD and enabled Azure Rights Management, use the Test-IRMConfiguration cmdlet to test Azure Rights Management functionality.</span></span> <span data-ttu-id="22f35-156">자세한 내용은 [테스트-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx)의 "예제 1"을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="22f35-156">For details, see "Example 1" in [Test-IRMConfiguration](https://technet.microsoft.com/library/dd979798%28v=exchg.150%29.aspx).</span></span>

## <a name="i-have-the-previous-version-of-ome-set-up-with-active-directory-rights-management-not-azure-information-protection-what-do-i-do"></a><span data-ttu-id="22f35-157">이전 버전의 OME가 Azure Information Protection이 아닌 Active Directory Rights Management로 설정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-157">I have the previous version of OME set up with Active Directory Rights Management not Azure Information Protection, what do I do?</span></span>
<span data-ttu-id="22f35-158"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="22f35-158"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="22f35-159">Active Directory Rights Management를 사용 하 여 기존 Office 365 메시지 암호화 메일 흐름 규칙을 계속 사용할 수 있지만 새 OME 기능을 구성 하거나 사용 하는 것은 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-159">You can continue to use your existing Office 365 Message Encryption mail flow rules with Active Directory Rights Management, but you can't configure or use the new OME capabilities.</span></span> <span data-ttu-id="22f35-160">대신 Azure Information Protection로 마이그레이션해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-160">Instead, you need to migrate to Azure Information Protection.</span></span> <span data-ttu-id="22f35-161">마이그레이션에 대 한 자세한 내용과 조직에서 수행 하는 작업에 대 한 자세한 내용은 [AD RMS에서 Azure Information Protection로 마이그레이션을](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="22f35-161">For information about migration and what this means for your organization, see [Migrating from AD RMS to Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/prepare-environment-adrms).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="22f35-162">다음 단계</span><span class="sxs-lookup"><span data-stu-id="22f35-162">Next steps</span></span>
<span data-ttu-id="22f35-163"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="22f35-163"><a name="importTPDs"> </a></span></span>

<span data-ttu-id="22f35-164">Azure 권한 관리 설치를 완료 한 후에 새 OME 기능을 사용 하도록 설정 하려면 [Azure Information Protection에 기본적으로 제공 되는 새로운 Office 365 메시지 암호화 기능 설정을](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="22f35-164">Once you've completed Azure Rights Management setup, if you want to enable the new OME capabilities, see [Set up new Office 365 Message Encryption capabilities built on top of Azure Information Protection.](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities)</span></span>
  
<span data-ttu-id="22f35-165">새 OME 기능을 사용 하도록 조직을 설정한 후에는 [새 OME 기능을 사용 하 여 전자 메일 메시지를 보호 하는 메일 흐름 규칙을 정의할](define-mail-flow-rules-to-encrypt-email.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="22f35-165">After you've set up your organization to use the new OME capabilities, you're ready to [Define mail flow rules to protect email messages with new OME capabilities](define-mail-flow-rules-to-encrypt-email.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="22f35-166">관련 항목</span><span class="sxs-lookup"><span data-stu-id="22f35-166">Related topics</span></span>
<span data-ttu-id="22f35-167"><a name="importTPDs"> </a></span><span class="sxs-lookup"><span data-stu-id="22f35-167"><a name="importTPDs"> </a></span></span>

[<span data-ttu-id="22f35-168">Office 365의 암호화</span><span class="sxs-lookup"><span data-stu-id="22f35-168">Encryption in Office 365</span></span>](encryption.md)
  
[<span data-ttu-id="22f35-169">Office 365의 암호화에 대한 기술 관련 세부 정보</span><span class="sxs-lookup"><span data-stu-id="22f35-169">Technical reference details about encryption in Office 365</span></span>](technical-reference-details-about-encryption.md)
  
[<span data-ttu-id="22f35-170">Azure 권한 관리란?</span><span class="sxs-lookup"><span data-stu-id="22f35-170">What is Azure Rights Management?</span></span>](https://docs.microsoft.com/information-protection/understand-explore/what-is-azure-rms)
