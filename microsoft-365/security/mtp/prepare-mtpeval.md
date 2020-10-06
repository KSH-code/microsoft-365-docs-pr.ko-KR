---
title: Microsoft Threat Protection 평가판 랩 환경 준비
description: Microsoft Threat Protection 평가판 랩 또는 파일럿 환경을 설정할 때 이해 관계자의 승인, 일정, 환경 고려 사항 및 채택 순서 준비
keywords: MTP 평가판 준비, MTP 파일럿 준비, MTP 파일럿 프로젝트 실행을 위한 준비, 파일럿 MTP 프로젝트, 배포, 준비, 관련자, 일정, 환경, 끝점, 서버, 관리, 도입
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: ac60415f38644c4630a181b1c8d696acced57ded
ms.sourcegitcommit: 9d8d071659e662c266b101377e24549963e43fef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2020
ms.locfileid: "48368004"
---
# <a name="prepare-your-microsoft-threat-protection-trial-lab-or-pilot-environment"></a><span data-ttu-id="3e6c5-104">Microsoft Threat Protection 평가판 랩 또는 파일럿 환경 준비</span><span class="sxs-lookup"><span data-stu-id="3e6c5-104">Prepare your Microsoft Threat Protection trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3e6c5-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="3e6c5-105">**Applies to:**</span></span>
- <span data-ttu-id="3e6c5-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="3e6c5-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="3e6c5-107">Microsoft Threat Protection 평가판 랩 또는 파일럿 환경을 만들고 배포 하는 과정은 다음 세 단계로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-107">Creating a Microsoft Threat Protection trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Microsoft Threat Protection 평가판 랩 또는 파일럿 환경 준비" />
      <br/><span data-ttu-id="3e6c5-109">1 단계: 준비 </a></span><span class="sxs-lookup"><span data-stu-id="3e6c5-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"  >
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Microsoft Threat Protection 평가판 랩 또는 파일럿 환경 설정" />
      <br/><span data-ttu-id="3e6c5-111">2 단계: 설치 </a></span><span class="sxs-lookup"><span data-stu-id="3e6c5-111">Phase 2: Setup </a></span></span><br>
        </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval">
        <img src="../../media/config-onboard.png" alt="Configure each Microsoft Threat Protection pillar" title="각 Microsoft Threat Protection 기둥 구성 및 끝점 온보드" />
      <br/><span data-ttu-id="3e6c5-113">3 단계: 온보드 & 구성</a></span><span class="sxs-lookup"><span data-stu-id="3e6c5-113">Phase 3: Configure & Onboard</a></span></span><br>
</td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
  </tr>
</table>

<span data-ttu-id="3e6c5-114">현재 준비 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-114">You're currently in the preparation phase.</span></span>


<span data-ttu-id="3e6c5-115">준비는 성공적인 배포의 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="3e6c5-116">이 섹션에서는 Microsoft Threat Protection 배포를 위한 시험 운용 랩 또는 파일럿 환경을 만들기 위해 준비할 때 고려해 야 할 사항을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-116">This section will guide you through what you need to consider as you prepare to create a trial lab or pilot environment for your Microsoft Threat Protection deployment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3e6c5-117">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="3e6c5-117">Prerequisites</span></span>
<span data-ttu-id="3e6c5-118">Microsoft Threat Protection을 프로 비전 하 고 사용 하기 위한 라이선스, 하드웨어 및 소프트웨어 요구 사항 및 기타 구성 설정에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-118">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span> <span data-ttu-id="3e6c5-119">Microsoft [Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites), [microsoft Defender atp](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), [OFFICE 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), [microsoft Cloud App Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)에 대 한 최소 요구 사항을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-119">See the minimum requirements for [Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites), [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), [Microsoft Cloud App Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites).</span></span>

## <a name="stakeholders-and-sign-off"></a><span data-ttu-id="3e6c5-120">관련자 및 승인</span><span class="sxs-lookup"><span data-stu-id="3e6c5-120">Stakeholders and sign-off</span></span>
<span data-ttu-id="3e6c5-121">다음 섹션에서는 평가를 수행할지 아니면 파일럿을 실행할지에 관계 없이 프로젝트와 관련 된 모든 관련자와 서명 하거나, 검토 하거나, 정보를 제공할 수 있는 모든 이해 관계자를 식별 하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-121">The following section serves to identify all the stakeholders that are involved in the project and who may need to sign-off, review, or stay informed, whether for evaluation or running a pilot.</span></span>

>[!NOTE]
><span data-ttu-id="3e6c5-122">모든 조직이 보안 조직 성숙도를 보유 하 고 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-122">Not all organizations might have the security organization maturity to have such roles.</span></span> <span data-ttu-id="3e6c5-123">이러한 경우 검토 및 승인 책임에 대 한 팀장 팀에 문의 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-123">In such case, consult with your leadership team on review and approval accountabilities.</span></span>

<span data-ttu-id="3e6c5-124">조직에 적합 한 아래 표에 관련자를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-124">Add stakeholders to the table below as appropriate for your organization.</span></span>

-   <span data-ttu-id="3e6c5-125">SO =이 프로젝트에 대 한 승인</span><span class="sxs-lookup"><span data-stu-id="3e6c5-125">SO = Sign-off on this project</span></span>

-   <span data-ttu-id="3e6c5-126">R =이 프로젝트를 검토 하 고 입력을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-126">R = Review this project and provide input</span></span>

-   <span data-ttu-id="3e6c5-127">I =이 프로젝트에 대 한 정보</span><span class="sxs-lookup"><span data-stu-id="3e6c5-127">I = Informed of this project</span></span>

| <span data-ttu-id="3e6c5-128">이름</span><span class="sxs-lookup"><span data-stu-id="3e6c5-128">Name</span></span>                 | <span data-ttu-id="3e6c5-129">역할</span><span class="sxs-lookup"><span data-stu-id="3e6c5-129">Role</span></span>                                                                                                                                                                                                          | <span data-ttu-id="3e6c5-130">작업</span><span class="sxs-lookup"><span data-stu-id="3e6c5-130">Action</span></span> |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| <span data-ttu-id="3e6c5-131">이름 및 전자 메일 입력</span><span class="sxs-lookup"><span data-stu-id="3e6c5-131">Enter name and email</span></span> | <span data-ttu-id="3e6c5-132">**최고 정보 보안 담당자 (CISO)** *새 기술 배포를 위해 조직 내에서 스폰서 역할을 하는 임원 담당자입니다.*</span><span class="sxs-lookup"><span data-stu-id="3e6c5-132">**Chief Information Security Officer (CISO)** *An executive representative who serves as sponsor inside the organization for the new technology deployment.*</span></span>                                                  | <span data-ttu-id="3e6c5-133">하면</span><span class="sxs-lookup"><span data-stu-id="3e6c5-133">SO</span></span>     |
| <span data-ttu-id="3e6c5-134">이름 및 전자 메일 입력</span><span class="sxs-lookup"><span data-stu-id="3e6c5-134">Enter name and email</span></span> | <span data-ttu-id="3e6c5-135">**사이버 (cdoc)의 머리** *이 변경 내용이 고객 보안 운영 팀의 프로세스와 부합 되는 방식을 정의 하는 방법을 담당 하는 cdoc 팀의 대표입니다.*</span><span class="sxs-lookup"><span data-stu-id="3e6c5-135">**Head of Cyber Defense Operations Center (CDOC)** *A representative from the CDOC team in charge of defining how this change is aligned with the processes in the customers security operations team.*</span></span>       | <span data-ttu-id="3e6c5-136">하면</span><span class="sxs-lookup"><span data-stu-id="3e6c5-136">SO</span></span>     |
| <span data-ttu-id="3e6c5-137">이름 및 전자 메일 입력</span><span class="sxs-lookup"><span data-stu-id="3e6c5-137">Enter name and email</span></span> | <span data-ttu-id="3e6c5-138">**보안 설계자** 는 *이 변경 내용이 조직의 핵심 보안 아키텍처에 부합 되는 방식을 정의 하는 방식으로 보안 팀의 담당자를 담당 합니다.*</span><span class="sxs-lookup"><span data-stu-id="3e6c5-138">**Security Architect** *A representative from the Security team in charge of defining how this change is aligned with the core Security architecture in the organization.*</span></span>                         | <span data-ttu-id="3e6c5-139">이력서</span><span class="sxs-lookup"><span data-stu-id="3e6c5-139">R</span></span>      |
| <span data-ttu-id="3e6c5-140">이름 및 전자 메일 입력</span><span class="sxs-lookup"><span data-stu-id="3e6c5-140">Enter name and email</span></span> | <span data-ttu-id="3e6c5-141">**회사 설계자** 는 *IT 팀의 담당자가 조직의 핵심 작업 사이트 아키텍처와이 변경 사항을 맞추는 방법을 정의 하는 작업을 담당 합니다.*</span><span class="sxs-lookup"><span data-stu-id="3e6c5-141">**Workplace Architect** *A representative from the IT team in charge of defining how this change is aligned with the core workplace architecture in the organization.*</span></span>                             | <span data-ttu-id="3e6c5-142">이력서</span><span class="sxs-lookup"><span data-stu-id="3e6c5-142">R</span></span>      |
| <span data-ttu-id="3e6c5-143">이름 및 전자 메일 입력</span><span class="sxs-lookup"><span data-stu-id="3e6c5-143">Enter name and email</span></span> | <span data-ttu-id="3e6c5-144">**보안 분석가** 는 *보안 작업 측면에서 검색 기능, 사용자 환경 및이 변경의 전반적인 유용성에 대 한 입력을 제공할 수 있는 cdoc 팀의 담당자입니다.*</span><span class="sxs-lookup"><span data-stu-id="3e6c5-144">**Security Analyst** *A representative from the CDOC team who can provide input on the detection capabilities, user experience, and overall usefulness of this change from a security operations perspective.*</span></span> | <span data-ttu-id="3e6c5-145">때</span><span class="sxs-lookup"><span data-stu-id="3e6c5-145">I</span></span>      |

## <a name="prepare-your-azure-active-directory"></a><span data-ttu-id="3e6c5-146">Azure Active Directory 준비</span><span class="sxs-lookup"><span data-stu-id="3e6c5-146">Prepare your Azure Active Directory</span></span>
<span data-ttu-id="3e6c5-147">Active Directory와 Azure Active Directory 간의 동기화를 이미 사용 하도록 설정한 경우에는이 단계를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-147">Skip this step if you have already enabled synchronization between Active Directory and Azure Active Directory on premises.</span></span> <span data-ttu-id="3e6c5-148">Azure Active Directory에서 기존 모범 사례 설명서를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-148">Review existing best practices documentation from Azure Active Directory.</span></span> <span data-ttu-id="3e6c5-149">다음 단계는 파일럿 Microsoft Threat Protection 프로젝트를 평가 하거나 실행 하도록 최적화 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-149">The following steps are optimized to evaluate or run a pilot Microsoft Threat Protection project.</span></span>

1. <span data-ttu-id="3e6c5-150">Azure **AD Connect**> [azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) 포털로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-150">Go to the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) portal > **Azure AD Connect**.</span></span> 
<span data-ttu-id="3e6c5-151">![Azure Active Directory 포털 페이지 이미지](../../media/mtp-eval-1.png)</span><span class="sxs-lookup"><span data-stu-id="3e6c5-151">![Image of Azure Active Directory portal page](../../media/mtp-eval-1.png)</span></span> <br> 

2. <span data-ttu-id="3e6c5-152">**Microsoft Azure Active Directory Connect** 에서 **다운로드** 를 클릭 하 고 도메인 컨트롤러로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-152">Click **Download** from **Microsoft Azure Active Directory Connect** and transfer it to your Domain Controller.</span></span>
<span data-ttu-id="3e6c5-153">![Azure 활성 Directoru 연결 다운로드 페이지 이미지](../../media/mtp-eval-2.png)</span><span class="sxs-lookup"><span data-stu-id="3e6c5-153">![Image of Azure Active Directoru Connect download page](../../media/mtp-eval-2.png)</span></span> <br>

3. <span data-ttu-id="3e6c5-154">도메인 컨트롤러에서 Azure Active Directory 연결 마법사를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-154">On the domain controller, follow the Azure Active Directory Connect wizard.</span></span> <span data-ttu-id="3e6c5-155">사용권 조항 및 개인 정보 취급 방침을 읽고 동의할 경우 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-155">Read the license terms and privacy notice and select the checkbox if you agree.</span></span> <span data-ttu-id="3e6c5-156">**계속**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-156">Click **Continue**.</span></span>
<span data-ttu-id="3e6c5-157">![Azure AD Connect 환영 페이지 이미지](../../media/mtp-eval-3.png)</span><span class="sxs-lookup"><span data-stu-id="3e6c5-157">![Image of Azure AD Connect welcome page](../../media/mtp-eval-3.png)</span></span> <br>

4. <span data-ttu-id="3e6c5-158">**빠른 설정**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-158">Navigate to **Express Settings**.</span></span>
<span data-ttu-id="3e6c5-159">![Express 설정 이미지 페이지](../../media/mtp-eval-4.png)</span><span class="sxs-lookup"><span data-stu-id="3e6c5-159">![Image of Express Settings page](../../media/mtp-eval-4.png)</span></span> <br>

5. <span data-ttu-id="3e6c5-160">전역 관리자 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-160">Enter your global administrator credentials.</span></span> <span data-ttu-id="3e6c5-161">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-161">Click **Next**.</span></span>
<span data-ttu-id="3e6c5-162">![전역 관리자 자격 증명을 입력 해야 하는 Azure AD 연결 페이지의 이미지](../../media/mtp-eval-5.png)</span><span class="sxs-lookup"><span data-stu-id="3e6c5-162">![Image of Connect to Azure AD page where you should enter your global administrator credentials](../../media/mtp-eval-5.png)</span></span> <br>

6. <span data-ttu-id="3e6c5-163">Active Directory 도메인 서비스 엔터프라이즈 관리자 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-163">Enter your Active Directory Domain Services enterprise administrator credentials.</span></span> <span data-ttu-id="3e6c5-164">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-164">Click **Next**.</span></span>
<span data-ttu-id="3e6c5-165">![자격 증명을 입력 해야 하는 AD DS 페이지에 연결 되는 이미지](../../media/mtp-eval-6.png)</span><span class="sxs-lookup"><span data-stu-id="3e6c5-165">![Image of Connect to AD DS page where you should enter your credentials](../../media/mtp-eval-6.png)</span></span> <br>

7. <span data-ttu-id="3e6c5-166">**설치** 를 클릭 하 여 구성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-166">Click **Install** to confirm the configuration.</span></span>
<span data-ttu-id="3e6c5-167">![구성 확인 페이지 이미지](../../media/mtp-eval-7.png)</span><span class="sxs-lookup"><span data-stu-id="3e6c5-167">![Image of configuration confirmation page](../../media/mtp-eval-7.png)</span></span> <br>

8. <span data-ttu-id="3e6c5-168">축 하 합니다, Azure Active Directory Connect를 구성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-168">Congratulations, you have successfully configured Azure Active Directory Connect.</span></span>
<span data-ttu-id="3e6c5-169">![성공적으로 구성 된 Azure Active Directory Connect 페이지 이미지](../../media/mtp-eval-8.png)</span><span class="sxs-lookup"><span data-stu-id="3e6c5-169">![Image of a successfully configured Azure Active Directory Connect page](../../media/mtp-eval-8.png)</span></span> <br>

<span data-ttu-id="3e6c5-170">이제 [Active Directory에 사용자 및 그룹을 추가](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) 하 고 [SAM 정책을 구성할](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-170">You can now [add users and groups to Active Directory](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) and [configure a SAM-R policy](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc).</span></span>  


## <a name="configuration-order"></a><span data-ttu-id="3e6c5-171">구성 순서</span><span class="sxs-lookup"><span data-stu-id="3e6c5-171">Configuration order</span></span>
<span data-ttu-id="3e6c5-172">아래 표에는 Microsoft에서 평가판 랩 또는 파일럿 환경 배포를 위한 Microsoft Threat Protection 구성 요소를 구성 하는 데 권장 되는 순서가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-172">The table below indicates the order Microsoft recommends for configuring the Microsoft Threat Protection components for your trial lab or pilot environment deployment.</span></span>

| <span data-ttu-id="3e6c5-173">구성 요소</span><span class="sxs-lookup"><span data-stu-id="3e6c5-173">Component</span></span>                               | <span data-ttu-id="3e6c5-174">설명</span><span class="sxs-lookup"><span data-stu-id="3e6c5-174">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="3e6c5-175">구성 순서 순위</span><span class="sxs-lookup"><span data-stu-id="3e6c5-175">Configuration order rank</span></span> |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
| <span data-ttu-id="3e6c5-176">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3e6c5-176">Office 365 Advanced Threat Protection</span></span>| <span data-ttu-id="3e6c5-177">Office 365 ATP는 전자 메일 메시지, 링크 (Url) 및 공동 작업 도구로 인해 야기 되는 악의적인 위협 으로부터 조직을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-177">Office 365 ATP safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> <br> [<span data-ttu-id="3e6c5-178">더 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-178">Learn more.</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)                                                                                                                                                                                                                                             | <span data-ttu-id="3e6c5-179">1 </span><span class="sxs-lookup"><span data-stu-id="3e6c5-179">1</span></span>                   |
|<span data-ttu-id="3e6c5-180">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3e6c5-180">Azure Advanced Threat Protection</span></span>|<span data-ttu-id="3e6c5-181">Azure ATP는 Active Directory 신호를 사용 하 여 조직에서 진행 되는 고급 위협, 손상 된 id 및 악의적인 참가자 작업을 식별, 감지 및 조사 합니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-181">Azure ATP uses Active Directory signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> <br> <span data-ttu-id="3e6c5-182">[자세히 알아보기](https://docs.microsoft.com/azure-advanced-threat-protection/).</span><span class="sxs-lookup"><span data-stu-id="3e6c5-182">[Learn more](https://docs.microsoft.com/azure-advanced-threat-protection/).</span></span>| <span data-ttu-id="3e6c5-183">2 </span><span class="sxs-lookup"><span data-stu-id="3e6c5-183">2</span></span> |
|<span data-ttu-id="3e6c5-184">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3e6c5-184">Microsoft Cloud App Security</span></span>| <span data-ttu-id="3e6c5-185">Microsoft Cloud App Security는 여러 클라우드에서 작동 하는 "CASB (Cloud Access Security Broker)"입니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-185">Microsoft Cloud App Security is a Cloud Access Security Broker (CASB) that operates on multiple clouds.</span></span> <span data-ttu-id="3e6c5-186">이를 통해 다양 한 가시성, 데이터 이동에 대 한 제어, 모든 클라우드 서비스에서 cyberthreats을 식별 하 고 공격 하는 정교한 분석이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-186">It provides rich visibility, control over data travel, and sophisticated analytics to identify and combat cyberthreats across all your cloud services.</span></span> <br> <span data-ttu-id="3e6c5-187">[자세히 알아보기](https://docs.microsoft.com/cloud-app-security/).</span><span class="sxs-lookup"><span data-stu-id="3e6c5-187">[Learn more](https://docs.microsoft.com/cloud-app-security/).</span></span>                                                                                                                                                                                                                                                                                                                                                                       |<span data-ttu-id="3e6c5-188">3 </span><span class="sxs-lookup"><span data-stu-id="3e6c5-188">3</span></span>                   |
|<span data-ttu-id="3e6c5-189">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3e6c5-189">Microsoft Defender Advanced Threat Protection</span></span> | <span data-ttu-id="3e6c5-190">Microsoft Defender ATP 엔드포인트 탐지 및 대응 기능은 실시간에 근접하고 조치가 가능한 고급 공격 탐지력을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-190">Microsoft Defender ATP endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="3e6c5-191">보안 분석가는 알림에 효과적으로 우선 순위를 지정하고, 침해의 전체 범위에 대한 가시성을 확보하고 위협을 수정하기 위한 대응 조치를 취할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-191">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span> <br> [<span data-ttu-id="3e6c5-192">더 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="3e6c5-192">Learn more.</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |<span data-ttu-id="3e6c5-193">4 </span><span class="sxs-lookup"><span data-stu-id="3e6c5-193">4</span></span>                   |                                                                                                                                                                                                                                    

## <a name="next-step"></a><span data-ttu-id="3e6c5-194">다음 단계</span><span class="sxs-lookup"><span data-stu-id="3e6c5-194">Next step</span></span>
|<span data-ttu-id="3e6c5-195">![2 단계: 설치](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="3e6c5-195">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="3e6c5-196">2 단계: 설치</span><span class="sxs-lookup"><span data-stu-id="3e6c5-196">Phase 2: Setup</span></span>](setup-mtpeval.md) | <span data-ttu-id="3e6c5-197">Microsoft Threat Protection 평가판 랩 또는 파일럿 환경 설정</span><span class="sxs-lookup"><span data-stu-id="3e6c5-197">Set up your Microsoft Threat Protection trial lab or pilot environment</span></span>
|:-------|:-----|

