---
title: Microsoft 365 데이터 손실 방지 온-프레미스 스캐너로 시작하기(미리 보기)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft 365 데이터 손실 방지 온-프레미스 스캐너 설정
ms.openlocfilehash: 242956a3c6469756481fb823340e715a210562af
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114176"
---
# <a name="get-started-with-the-data-loss-prevention-on-premises-scanner-preview"></a><span data-ttu-id="bd9dc-103">데이터 손실 방지 온-프레미스 스캐너로 시작하기(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="bd9dc-103">Get started with the data loss prevention on-premises scanner (preview)</span></span>

<span data-ttu-id="bd9dc-104">이 문서에서는 Microsoft 365 데이터 손실 방지 온-프레미스 스캐너의 필수 구성 요소 및 구성에 관한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-104">This article walks you through the prerequisites and configuration for the Microsoft 365 data loss prevention on-premises scanner.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="bd9dc-105">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="bd9dc-105">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="bd9dc-106">SKU/구독 라이선싱</span><span class="sxs-lookup"><span data-stu-id="bd9dc-106">SKU/subscriptions licensing</span></span>

<span data-ttu-id="bd9dc-107">DLP 온-프레미스 스캐너를 시작하기 전에 [Microsoft 365 구독](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)과 추가 기능을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-107">Before you get started with DLP on-premises scanner, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="bd9dc-108">미리 보기에 참여하려면, DLP 규칙을 설정하는 관리자 계정에 다음 라이선스 중 한 가지가 할당되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-108">To participate in the preview the admin account that sets up the DLP rules must be assigned one of the following licenses:</span></span>

- <span data-ttu-id="bd9dc-109">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="bd9dc-109">Microsoft 365 E5</span></span>
- <span data-ttu-id="bd9dc-110">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="bd9dc-110">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="bd9dc-111">Microsoft 365 E5 정보 보호 및 거버넌스</span><span class="sxs-lookup"><span data-stu-id="bd9dc-111">Microsoft 365 E5 Information Protection & Governance</span></span> 


<span data-ttu-id="bd9dc-112">전체 라이선싱에 대한 자세한 내용은 [보안 & 준수에 대한 Microsoft 365 라이선스 지침](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-112">For full licensing details see: [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)</span></span>

### <a name="permissions"></a><span data-ttu-id="bd9dc-113">사용 권한</span><span class="sxs-lookup"><span data-stu-id="bd9dc-113">Permissions</span></span>


<span data-ttu-id="bd9dc-114">DLP 온-프레미스 스캐너의 데이터는 [활동 탐색기](data-classification-activity-explorer.md)에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-114">Data from DLP on-premises scanner can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="bd9dc-115">활동 탐색기에 대한 사용 권한을 부여하는 네 개의 역할이 있습니다. 데이터에 액세스하는 데 사용하는 계정은 해당 역할 중 하나의 구성원이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-115">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="bd9dc-116">전역 관리자</span><span class="sxs-lookup"><span data-stu-id="bd9dc-116">Global administrator</span></span>
- <span data-ttu-id="bd9dc-117">준수 관리자</span><span class="sxs-lookup"><span data-stu-id="bd9dc-117">Compliance administrator</span></span>
- <span data-ttu-id="bd9dc-118">보안 관리자</span><span class="sxs-lookup"><span data-stu-id="bd9dc-118">Security administrator</span></span>
- <span data-ttu-id="bd9dc-119">규정 준수 데이터 관리자</span><span class="sxs-lookup"><span data-stu-id="bd9dc-119">Compliance data administrator</span></span>

### <a name="dlp-on-premises-scanner-prerequisites"></a><span data-ttu-id="bd9dc-120">DLP 온-프레미스 스캐너에 대한 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="bd9dc-120">DLP on-premises scanner prerequisites</span></span>

- <span data-ttu-id="bd9dc-p103">Azure Information Protection (AIP) 스캐너는 DLP 정책 일치 및 정책 적용을 구현합니다. 스캐너는 AIP 클라이언트의 일부로 설치되어 사용자의 설치가 AIP, AIP 클라이언트 및 AIP 통합 레이블 스캐너의 모든 필수 구성 요소를 갖춰야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-p103">The Azure Information Protection (AIP) scanner implements DLP policy matching and policy enforcement. The scanner is installed as part of the AIP client so your installation must meet all the prerequisites  for AIP, the AIP client, and the AIP unified labeling scanner.</span></span>
- <span data-ttu-id="bd9dc-123">AIP 클라이언트 및 스캐너를 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-123">Deploy the AIP  client and scanner.</span></span> <span data-ttu-id="bd9dc-124">[AIP 통합 레이블 지정 클라이언트 설치](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) 및 []에 대한 자세한 내용은 [Azure Information Protection 통합 레이블 지정 스캐너 구성 및 설치](/azure/information-protection/deploy-aip-scanner-configure-install)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-124">For more information [Install the AIP unified labeling client](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) and [], see [Configuring and installing the Azure Information Protection unified labeling scanner](/azure/information-protection/deploy-aip-scanner-configure-install).</span></span>
- <span data-ttu-id="bd9dc-125">모든 검색 규칙이 중요한 정보 유형만을 기반으로 할지라도 테넌트에 하나 이상의 레이블 및 정책이 게시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-125">There must be at least one label and policy published in the tenant, even if all your detection rules are based on sensitive information types only.</span></span>

## <a name="deploy-the-dlp-on-premises-scanner"></a><span data-ttu-id="bd9dc-126">DLP 온-프레미스 스캐너 배포</span><span class="sxs-lookup"><span data-stu-id="bd9dc-126">Deploy the DLP on-premises scanner</span></span>

1. <span data-ttu-id="bd9dc-127">[AIP 통합 레이블 지정 클라이언트 설치](/azure/information-protection/rms-client/install-unifiedlabelingclient-app) 절차를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-127">Follow the procedures in [Install the AIP unified labeling client](/azure/information-protection/rms-client/install-unifiedlabelingclient-app).</span></span> 
2. <span data-ttu-id="bd9dc-128">[Azure Information Protection 통합 레이블 지정 스캐너 구성 및 설치](/azure/information-protection/deploy-aip-scanner-configure-install)절차를 따라 스캐너 설치를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-128">Follow the procedures in [Configuring and installing the Azure Information Protection unified labeling scanner](/azure/information-protection/deploy-aip-scanner-configure-install) to complete the scanner installation.</span></span>
    1. <span data-ttu-id="bd9dc-129">네트워크 검색 작업 구성은 선택적 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-129">Network discovery jobs configuration is an optional step.</span></span> <span data-ttu-id="bd9dc-130">이를 건너뛰고 콘텐츠 스캔 작업에서 스캔할 특정 리포지토리를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-130">You can skip it and define specific repositories to be scanned in your content scan job.</span></span>
    2. <span data-ttu-id="bd9dc-131">콘텐츠 스캔 작업을 만들고 DLP 엔진으로 평가해야 하는 파일을 호스트하는 리포지토리를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-131">You must create content scan job and specify the repositories that host files that need to be evaluated by the DLP engine.</span></span>
    3. <span data-ttu-id="bd9dc-132">만든 콘텐츠 스캔 작업의 DLP 규칙을 사용하도록 설정하고, DLP 적용 단계로 직접 진행하지 않는 이상 옵션을 **끄기** 로 **적용** 하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-132">Enable DLP rules in the created Content scan job, and set the **Enforce** option to **Off**, unless you want to proceed directly to the DLP enforcement stage.</span></span>
3. <span data-ttu-id="bd9dc-p106">콘텐츠 스캔 작업이 올바른 클러스터에 할당되어 있는지 확인합니다. 아직 콘텐츠 스캔 작업을 만들지 않았을 경우 새 스캔 작업을 만들고 공개 미리 보기 버전을 실행하는 스캐너 노드가 포함된 클러스터에 이를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-p106">Verify that you content scan job is assigned to the right cluster. If you still did not create a content scan job create a new one and assign it to the cluster that contains the scanner nodes that run the public preview version.</span></span>

4. <span data-ttu-id="bd9dc-135">[Azure Portal 내 Azure Information Protection 확장](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade)에 연결하고 스캔을 수행하는 콘텐츠 스캔 작업으로 리포지토리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-135">Connect to the [Azure Information Protection extension in Azure portal](https://portal.azure.com/#blade/Microsoft_Azure_InformationProtection/DataClassGroupEditBlade/scannerProfilesBlade) and add your repositories to the content scan job that will perform the scan.</span></span>

5. <span data-ttu-id="bd9dc-136">다음 중 하나를 실행하여 스캔을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-136">Do one of the following to run your scan:</span></span>
    1. <span data-ttu-id="bd9dc-137">스캐너 일정 설정</span><span class="sxs-lookup"><span data-stu-id="bd9dc-137">set the scanner schedule</span></span>
    1. <span data-ttu-id="bd9dc-138">포털에서 수동 **지금 스캔** 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-138">use the manual **Scan Now** option in the portal</span></span>
    1. <span data-ttu-id="bd9dc-139">또는 **Start-AIPScan** PowerShell cmdlet을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-139">or run **Start-AIPScan** PowerShell cmdlet</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="bd9dc-140">스캐너는 기본적으로 리포지토리의 델타 스캔을 실행하며, 파일이 변경되거나 전체 다시 스캔을 시작하지 않는 한 이전 스캔 싸이클에서 이미 스캔된 파일은 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-140">Remember that the scanner runs a delta scan of the repository by default and the files that were already scanned in the previous scan cycle will be skipped unless the file was changed or you initiated a full rescan.</span></span> <span data-ttu-id="bd9dc-141">UI에서 **모든 파일 다시 스캔** 옵션을 사용하거나 **Start-AIPScan-Reset** 을 실행하여 전체 다시 스캔을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-141">Full rescan can be initiated by using **Rescan all files** option in the UI or by running **Start-AIPScan-Reset**.</span></span>

6.  <span data-ttu-id="bd9dc-142">Microsoft 365 규정 준수 센터에서 [데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention?viewid=policies)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-142">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) in the Microsoft 365 Compliance center.</span></span>

7. <span data-ttu-id="bd9dc-143">**정책을 만들기** 를 선택하고 테스트 DLP 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-143">Choose **Create policy** and create a test DLP policy.</span></span> <span data-ttu-id="bd9dc-144">정책을 만드는데 도움이 필요한 경우 [서식 파일에서 DLP 정책 만들기](create-a-dlp-policy-from-a-template.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-144">See [Create a DLP policy from a template](create-a-dlp-policy-from-a-template.md) if you need help creating a policy.</span></span> <span data-ttu-id="bd9dc-145">이 기능에 대해 잘 알게 될 때까지 테스트 실행을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-145">Be sure to run it in test until you are comfortable with this feature.</span></span> <span data-ttu-id="bd9dc-146">정책에 다음 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-146">Use these parameters for your policy:</span></span>
    1. <span data-ttu-id="bd9dc-147">필요한 경우 DLP 온-프레미스 스캐너 규칙을 특정 위치로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-147">Scope the DLP on-premises scanner rule to specific locations if needed.</span></span> <span data-ttu-id="bd9dc-148">**위치** 를 **모든 위치** 로 지정했다면 스캐너로 스캔한 모든 파일에는 DLP 규칙 일치 및 적용이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-148">If you scope **locations** to **All**, all files scanned by the scanner will be subject to the DLP rule matching and enforcement.</span></span>
    1. <span data-ttu-id="bd9dc-149">위치를 지정할 때 배제 또는 포함 목록을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-149">When specifying the locations, you can use either exclusion or inclusion list.</span></span> <span data-ttu-id="bd9dc-150">공개 미리 보기 동안에는 두 가지를 모두 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-150">During public preview you cannot set both of them.</span></span> <span data-ttu-id="bd9dc-151">규칙이 포함 목록에 있는 패턴 중 하나와 일치하는 경로와만 관련이 있거나, 또는 포함 목록에 있는 패턴과 일치하는 파일을 제외한 모든 파일과 관련이 있는 것으로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-151">You can either define that the rule is relevant only to paths matching one of the patterns listed in inclusion list or, all files, except the files matching the pattern listed in inclusion list.</span></span> <span data-ttu-id="bd9dc-152">지원되는 로컬 경로가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-152">No local paths are supported.</span></span> <span data-ttu-id="bd9dc-153">다음은 유효한 경로의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-153">Here are some examples of valid paths:</span></span>
      - <span data-ttu-id="bd9dc-154">\\\server\share</span><span class="sxs-lookup"><span data-stu-id="bd9dc-154">\\\server\share</span></span>
      - <span data-ttu-id="bd9dc-155">\\\server\share\folder1\subfolderabc</span><span class="sxs-lookup"><span data-stu-id="bd9dc-155">\\\server\share\folder1\subfolderabc</span></span>
      - <span data-ttu-id="bd9dc-156">\*\\folder1</span><span class="sxs-lookup"><span data-stu-id="bd9dc-156">\*\\folder1</span></span>
      - <span data-ttu-id="bd9dc-157">\*secret\*.docx</span><span class="sxs-lookup"><span data-stu-id="bd9dc-157">\*secret\*.docx</span></span>
      - <span data-ttu-id="bd9dc-158">\*secret\*.\*</span><span class="sxs-lookup"><span data-stu-id="bd9dc-158">\*secret\*.\*</span></span>
      - <span data-ttu-id="bd9dc-159"> https:// sp2010.local/sites/HR</span><span class="sxs-lookup"><span data-stu-id="bd9dc-159">https:// sp2010.local/sites/HR</span></span>
      - <span data-ttu-id="bd9dc-160"> https://\*/HR</span><span class="sxs-lookup"><span data-stu-id="bd9dc-160">https://\*/HR</span></span> 
    3. <span data-ttu-id="bd9dc-161">다음은 허용되지 않는 값의 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-161">Here are some examples of unacceptable values use:</span></span>
      - \*
      - <span data-ttu-id="bd9dc-162">\*\\a</span><span class="sxs-lookup"><span data-stu-id="bd9dc-162">\*\\a</span></span>
      - <span data-ttu-id="bd9dc-163">Aaa</span><span class="sxs-lookup"><span data-stu-id="bd9dc-163">Aaa</span></span>
      - <span data-ttu-id="bd9dc-164">c:</span><span class="sxs-lookup"><span data-stu-id="bd9dc-164">c:</span></span>\
      - <span data-ttu-id="bd9dc-165">C:\test</span><span class="sxs-lookup"><span data-stu-id="bd9dc-165">C:\test</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd9dc-166">제외 목록이 포함 목록보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-166">The exclusion list takes precedence over the inclusions list.</span></span>

### <a name="viewing-dlp-on-premises-scanner-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="bd9dc-167">DLP 경고 관리 대시보드에서 DLP 온-프레미스 스캐너 경고 보기</span><span class="sxs-lookup"><span data-stu-id="bd9dc-167">Viewing DLP on-premises scanner alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="bd9dc-168">Microsoft 365 규정 준수 센터에서 [데이터 손실 방지 페이지](https://compliance.microsoft.com/datalossprevention?viewid=policies)를 열고 **경고** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-168">Open the [Data loss prevention page](https://compliance.microsoft.com/datalossprevention?viewid=policies) in the Microsoft 365 Compliance center and select **Alerts**.</span></span>

2. <span data-ttu-id="bd9dc-169">엔드포인트 DLP 정책에 대한 경고를 보려면 [DLP 정책을 구성하고 경고를 보는 방법](dlp-configure-view-alerts-policies.md)의 절차를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-169">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>

### <a name="viewing-dlp-on-premises-scanner-in-activity-explorer-and-audit-log"></a><span data-ttu-id="bd9dc-170">활동 탐색기 및 감사 로그에서 DLP 온-프레미스 스캐너 보기</span><span class="sxs-lookup"><span data-stu-id="bd9dc-170">Viewing DLP on-premises scanner in activity explorer and audit log</span></span>

> [!NOTE]
> <span data-ttu-id="bd9dc-171">온-프레미스 스캐너를 사용하려면 감사를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-171">The on-premises scanner requires that auditing be enabled.</span></span> <span data-ttu-id="bd9dc-172">Microsoft 365 감사는 기본적으로 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-172">In Microsoft 365 auditing is enabled by default.</span></span>

1. <span data-ttu-id="bd9dc-173">Microsoft 365 규정 준수 센터에서 도메인에 대한 [데이터 분류 페이지](https://compliance.microsoft.com/dataclassification?viewid=overview)를 열고 활동 탐색기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-173">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and select Activity explorer.</span></span>

2. <span data-ttu-id="bd9dc-174">[활동 탐색기 시작하기](data-classification-activity-explorer.md)의 절차를 참조하여 온-프레미스 스캐너 위치에 대한 모든 데이터에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-174">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your on-premises scanner locations.</span></span>

3. <span data-ttu-id="bd9dc-175">[규정 준수 센터의 감사 로그](https://security.microsoft.com/auditlogsearch)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-175">Open the [Audit log in the Compliance center](https://security.microsoft.com/auditlogsearch).</span></span> <span data-ttu-id="bd9dc-176">공개 미리 보기 동안 DLP 규칙 일치 항목은 감사 로그 UI에서 확인할 수 있으며, [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell을 이용하여 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-176">During the public preview the DLP rule matches are available in Audit log UI or accessible by [Search-UnifiedAuditLog](/powershell/module/exchange/search-unifiedauditlog?view=exchange-ps) PowerShell</span></span> 


## <a name="next-steps"></a><span data-ttu-id="bd9dc-177">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bd9dc-177">Next steps</span></span>
<span data-ttu-id="bd9dc-178">이제 DLP 온-프레미스 위치에 대한 테스트 정책을 배포하였고 활동 탐색기에서 활동 데이터를 볼 수 있으므로, 중요한 항목을 보호하는 DLP 정책을 만드는 다음 단계로 진행할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bd9dc-178">Now that you have deployed a test policy for DLP on-premises locations and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="bd9dc-179">DLP 온-프레미스 사용하기(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="bd9dc-179">Using DLP on-premises (preview)</span></span>](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a><span data-ttu-id="bd9dc-180">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd9dc-180">See also</span></span>

- [<span data-ttu-id="bd9dc-181">DLP 온-프레미스 스캐너에 대한 자세한 정보(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="bd9dc-181">Learn about DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="bd9dc-182">DLP 온-프레미스 스캐너 사용하기(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="bd9dc-182">Use DLP on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-use.md)
- [<span data-ttu-id="bd9dc-183">데이터 손실 방지에 대한 자세한 정보</span><span class="sxs-lookup"><span data-stu-id="bd9dc-183">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="bd9dc-184">DLP 정책 만들기, 테스트 및 조정</span><span class="sxs-lookup"><span data-stu-id="bd9dc-184">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="bd9dc-185">활동 탐색기 시작하기</span><span class="sxs-lookup"><span data-stu-id="bd9dc-185">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="bd9dc-186">Microsoft 365 구독</span><span class="sxs-lookup"><span data-stu-id="bd9dc-186">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)