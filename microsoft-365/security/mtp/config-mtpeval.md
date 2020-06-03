---
title: 평가판 랩 환경용 Microsoft Threat Protection 핵심 요소로 구성
description: 평가판 랩 환경용 Microsoft Threat Protection 핵심 요소로, Office 365 ATP, Azure ATP, Microsoft Cloud App Security 및 Microsoft Defender ATP를 구성 합니다.
keywords: microsoft threat Protection 평가판, Microsoft Threat Protection 평가판 구성, microsoft threat protection 핵심 요소로, Microsoft Threat Protection 핵심 요소로을 구성 합니다.
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: be92bfe8fc4f544f0554f99d147bfc90bf569d57
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498462"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-environment"></a><span data-ttu-id="7e9ca-104">평가판 랩 환경용 Microsoft Threat Protection 핵심 요소로 구성</span><span class="sxs-lookup"><span data-stu-id="7e9ca-104">Configure Microsoft Threat Protection pillars for your trial lab environment</span></span>

<span data-ttu-id="7e9ca-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7e9ca-105">**Applies to:**</span></span>
- <span data-ttu-id="7e9ca-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="7e9ca-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="7e9ca-107">Microsoft Threat Protection 평가판 랩 환경을 만들고 배포 하는 과정은 다음 세 단계로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Microsoft Threat Protection 평가판 랩 환경 준비" />
      <br/><span data-ttu-id="7e9ca-109">1 단계: 준비</a></span><span class="sxs-lookup"><span data-stu-id="7e9ca-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Microsoft Threat Protection 평가판 랩 환경 설정" />
      <br/><span data-ttu-id="7e9ca-111">2 단계: 설치</a></span><span class="sxs-lookup"><span data-stu-id="7e9ca-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Microsoft Threat Protection 평가판 랩 환경 및 온보드 끝점에 대해 각 Microsoft Threat Protection를 구성 합니다." />
      <br/><span data-ttu-id="7e9ca-113">3 단계: 온보드 & 구성</a></span><span class="sxs-lookup"><span data-stu-id="7e9ca-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="7e9ca-114">현재 구성 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-114">You are currently in the configuration phase.</span></span>


<span data-ttu-id="7e9ca-115">준비는 성공적인 배포의 핵심입니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="7e9ca-116">이 문서에서는 Microsoft Defender ATP 배포를 준비할 때 고려해 야 할 사항을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="7e9ca-117">Microsoft Threat Protection 핵심 요소로</span><span class="sxs-lookup"><span data-stu-id="7e9ca-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="7e9ca-118">Microsoft Threat Protection은 핵심 요소로 4 개로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="7e9ca-119">한 번에 네트워크 조직의 보안에 대 한 가치를 제공할 수 있지만 Microsoft Threat Protection 핵심 요소로 4 개를 사용 하도록 설정 하면 조직에 가장 많은 값이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>

![<span data-ttu-id="7e9ca-120">사용자, Azure Advanced threat protection, 끝점에 대 한 위협 보호 솔루션, Microsoft Defender Advanced Threat Protection, 클라우드 앱, Microsoft Cloud App Security 및 data의 경우 Office 365 Advanced Threat Protection of_Microsoft</span><span class="sxs-lookup"><span data-stu-id="7e9ca-120">Image of_Microsoft Threat Protection solution for users, Azure Advanced Threat Protection, for endpoints Microsoft Defender Advanced Threat Protection, for cloud apps, Microsoft Cloud App Security, and for data, Office 365 Advanced Threat Protection</span></span>  ](../../media/mtp-eval-31.png) <br>

<span data-ttu-id="7e9ca-121">이 섹션에서는 다음을 구성할 수 있도록 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="7e9ca-122">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7e9ca-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="7e9ca-123">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7e9ca-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="7e9ca-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="7e9ca-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="7e9ca-125">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7e9ca-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="7e9ca-126">Office 365 Advanced Threat Protection 구성</span><span class="sxs-lookup"><span data-stu-id="7e9ca-126">Configure Office 365 Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="7e9ca-127">이미 Office 365 Advanced Threat Protection을 사용 하도록 설정한 경우에는이 단계를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-127">Skip this step if you have already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="7e9ca-128">이러한 설정 중 일부를 결정 하는 데 도움이 되는 *Office 365 Advanced Threat Protection 권장 구성 분석기 (ORCA)* 라는 PowerShell 모듈이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-128">There is a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="7e9ca-129">ORCAReport에서 관리자 권한으로 실행 하는 경우, get-스팸 방지, 피싱 및 기타 메시지 바이러스 백신 설정을 평가 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="7e9ca-130">이 모듈은에서 다운로드할 수 있습니다 https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="7e9ca-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="7e9ca-131">[Office 365 보안 & 준수 센터](https://protection.office.com/homepage)  >  **위협 관리**  >  **정책**으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>
<span data-ttu-id="7e9ca-132">![이미지 of_Office 365 보안 & 준수 센터 위협 관리 정책 페이지](../../media/mtp-eval-32.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-132">![Image of_Office 365 Security & Compliance Center Threat management policy page](../../media/mtp-eval-32.png)</span></span> <br>
 
2. <span data-ttu-id="7e9ca-133">**ATP 피싱 방지**를 클릭 하 고 정책 이름과 설명을 **작성** 하 여 채웁니다 .를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="7e9ca-134">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-134">Click **Next**.</span></span>
<span data-ttu-id="7e9ca-135">![이미지 of_Office 365 보안 & 준수 센터 정책 이름을 지정할 수 있는 피싱 방지 정책 페이지](../../media/mtp-eval-33.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-135">![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can name your policy](../../media/mtp-eval-33.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="7e9ca-136">고급 ATP 피싱 방지 정책을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="7e9ca-137">**Advanced 피싱 임계값** 을 **2-적극적**으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>
<br>

3. <span data-ttu-id="7e9ca-138">**조건 추가** 드롭다운 메뉴를 클릭 하 고 도메인을 받는 사람 도메인으로 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="7e9ca-139">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-139">Click **Next**.</span></span>
<span data-ttu-id="7e9ca-140">![이미지 of_Office 365 보안 & 준수 센터 피싱 방지 정책 페이지로, 해당 응용 프로그램에 조건을 추가할 수 있습니다.](../../media/mtp-eval-34.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-140">![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can add a condition for its application](../../media/mtp-eval-34.png)</span></span> <br>
 
4. <span data-ttu-id="7e9ca-141">설정을 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-141">Review your settings.</span></span> <span data-ttu-id="7e9ca-142">**이 정책 만들기** 를 클릭 하 여 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-142">Click **Create this policy** to confirm.</span></span> 
<span data-ttu-id="7e9ca-143">![이미지 of_Office 365 보안 & 준수 센터 피싱 방지 정책 페이지에서 설정을 검토 하 고이 정책 만들기 단추를 클릭할 수 있습니다.](../../media/mtp-eval-35.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-143">![Image of_Office 365 Security & Compliance Center anti-phishing policy page where you can review your settings and click the create this policy button](../../media/mtp-eval-35.png)</span></span> <br>
 
5. <span data-ttu-id="7e9ca-144">**Atp 안전한 첨부 파일** 을 선택 하 고 **SharePoint, OneDrive 및 Microsoft 팀에 게 atp 설정** 옵션을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>  
<span data-ttu-id="7e9ca-145">![이미지 of_Office 365 보안 & 준수 센터 페이지에서 SharePoint, OneDrive 및 Microsoft 팀에 대 한 ATP를 설정할 수 있습니다.](../../media/mtp-eval-36.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-145">![Image of_Office 365 Security & Compliance Center page where you can turn on ATP for SharePoint, OneDrive, and Microsoft Teams](../../media/mtp-eval-36.png)</span></span> <br>

6. <span data-ttu-id="7e9ca-146">+ 아이콘을 클릭 하 여 새 안전한 첨부 파일 정책을 만들려면 도메인에 받는 사람 도메인으로 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="7e9ca-147">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-147">Click **Save**.</span></span>
<span data-ttu-id="7e9ca-148">![이미지 of_Office 365 보안 & 준수 센터 페이지 새 안전한 첨부 파일 정책 만들기](../../media/mtp-eval-37.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-148">![Image of_Office 365 Security & Compliance Center page where you can create a new create a new safe attachment policy](../../media/mtp-eval-37.png)</span></span> <br>
 
7. <span data-ttu-id="7e9ca-149">다음으로 **ATP 안전한 링크** 정책을 선택 하 고 연필 아이콘을 클릭 하 여 기본 정책을 편집 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="7e9ca-150">**사용자가 안전 링크를 클릭 하면 추적 안 함** 옵션이 선택 되어 있지 않은 동안 나머지 옵션이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="7e9ca-151">자세한 내용은 [안전한 링크 설정을](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) for details.</span></span> <span data-ttu-id="7e9ca-152">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-152">Click **Save**.</span></span> 
<span data-ttu-id="7e9ca-153">![Image of_Office 365 보안 & 준수 센터 페이지-사용자가 안전한 클릭을 선택 하지 않은 경우 옵션을 추적 하지 않습니다.](../../media/mtp-eval-38.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-153">![Image of_Office 365 Security & Compliance Center page which shows that the option Do not track when users click safe is not selected](../../media/mtp-eval-38.png)</span></span> <br>

9. <span data-ttu-id="7e9ca-154">다음으로, **맬웨어 방지** 정책을 선택 하 고 기본값을 선택한 다음 연필 아이콘을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="7e9ca-155">**설정을** 클릭 하 고 **예를 선택 하 고 기본 알림 텍스트를 사용** 하 여 **맬웨어 검색 응답**을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="7e9ca-156">**일반 첨부 파일 형식 필터** 를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="7e9ca-157">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-157">Click **Save**.</span></span>
<br><span data-ttu-id="7e9ca-158">![Image of_Office 365 보안 & 준수 센터 페이지에서 맬웨어 검색 응답이 기본 알림과 일반 첨부 파일 유형 필터를 사용 하 여 켜져 있음을 보여 줍니다.](../../media/mtp-eval-39.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-158">![Image of_Office 365 Security & Compliance Center page which shows that the malware detection response is turned on with default notification and the common attachment types filter is turned on](../../media/mtp-eval-39.png)</span></span> <br>
  
11. <span data-ttu-id="7e9ca-159">[Office 365 Security & 준수 센터](https://protection.office.com/homepage)  >  **검색**  >  **감사 로그 검색** 및 감사 설정으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>  
<span data-ttu-id="7e9ca-160">![이미지 of_Office 365 보안 & 준수 센터 페이지에서 감사 로그 검색을 설정할 수 있습니다.](../../media/mtp-eval-40.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-160">![Image of_Office 365 Security & Compliance Center page where you can turn on the Audit log search](../../media/mtp-eval-40.png)</span></span> <br>

12. <span data-ttu-id="7e9ca-161">Office 365 ATP와 Microsoft Defender ATP를 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="7e9ca-162">[Office 365 Security & 준수 센터](https://protection.office.com/homepage)  >  **Threat management**  >  **Explorer** 로 이동 하 여 화면의 오른쪽 위 모서리에 있는 **wdatp 설정을** 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="7e9ca-163">Microsoft Defender ATP 연결 대화 상자에서 **WINDOWS ATP에 연결**을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>
<span data-ttu-id="7e9ca-164">![이미지 of_Office 365 보안 & 준수 센터 페이지에서 Windows Defender ATP 연결을 설정할 수 있습니다.](../../media/mtp-eval-41.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-164">![Image of_Office 365 Security & Compliance Center page where you can turn Windows Defender ATP connection on](../../media/mtp-eval-41.png)</span></span> <br>

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="7e9ca-165">Azure Advanced Threat Protection 구성</span><span class="sxs-lookup"><span data-stu-id="7e9ca-165">Configure Azure Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="7e9ca-166">Azure Advanced Threat Protection을 이미 사용 하도록 설정한 경우에는이 단계를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-166">Skip this step if you have already enabled Azure Advanced Threat Protection</span></span>


1. <span data-ttu-id="7e9ca-167">[Microsoft 365 보안 센터로](https://security.microsoft.com/info) 이동 하 > **기타 리소스**  >  **Azure Advanced Threat Protection**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>
<span data-ttu-id="7e9ca-168">![이미지 of_Microsoft 365 Azure Advanced Threat Protection을 여는 옵션이 있는 보안 센터 페이지](../../media/mtp-eval-42.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-168">![Image of_Microsoft 365 Security Center page where there's an option to open Azure Advanced Threat Protection](../../media/mtp-eval-42.png)</span></span> <br>

2. <span data-ttu-id="7e9ca-169">**만들기** 를 클릭 하 여 Azure Advanced Threat Protection 마법사를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 
<br><span data-ttu-id="7e9ca-170">![만들기 단추를 클릭 해야 하는 고급 위협 방지 마법사 페이지를 of_Azure 합니다.](../../media/mtp-eval-43.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-170">![Image of_Azure Advanced Threat Protection wizard page where you should click Create button](../../media/mtp-eval-43.png)</span></span> <br>

3. <span data-ttu-id="7e9ca-171">**Active Directory 포리스트에 연결 하려면 사용자 이름 및 암호 입력**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  
<span data-ttu-id="7e9ca-172">![이미지 of_Azure Advanced Threat Protection 시작 페이지](../../media/mtp-eval-44.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-172">![Image of_Azure Advanced Threat Protection welcome page](../../media/mtp-eval-44.png)</span></span> <br>

4. <span data-ttu-id="7e9ca-173">Active Directory 온-프레미스 자격 증명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="7e9ca-174">이 계정에는 Active Directory에 대 한 읽기 액세스 권한이 있는 모든 사용자 계정이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-174">This can be any user account that has read access to Active Directory.</span></span>
<span data-ttu-id="7e9ca-175">![자격 증명을 입력 해야 하는 Advanced Threat Protection 디렉터리 서비스 페이지 이미지 of_Azure](../../media/mtp-eval-45.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-175">![Image of_Azure Advanced Threat Protection Directory services page where you should put your credentials](../../media/mtp-eval-45.png)</span></span> <br>

5. <span data-ttu-id="7e9ca-176">그런 다음 **센서 설정 다운로드** 및 도메인 컨트롤러로 파일 전송을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span> 
<span data-ttu-id="7e9ca-177">![센서 설정 다운로드를 선택할 수 있는 고급 위협 방지 페이지 of_Azure](../../media/mtp-eval-46.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-177">![Image of_Azure Advanced Threat Protection page where you can select Download Sensor Setup](../../media/mtp-eval-46.png)</span></span> <br>

6. <span data-ttu-id="7e9ca-178">Azure ATP 센서 설정을 실행 하 고 마법사 팔 로우를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>
<br><span data-ttu-id="7e9ca-179">![Azure ATP 센서 마법사를 따르려면 다음을 클릭 해야 하는 Advanced Threat Protection 페이지 of_Azure 합니다.](../../media/mtp-eval-47.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-179">![Image of_Azure Advanced Threat Protection page where you should click next to follow the Azure ATP sensor wizard](../../media/mtp-eval-47.png)</span></span> <br>
 
7. <span data-ttu-id="7e9ca-180">센서 배포 유형에서 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-180">Click **Next** at the sensor deployment type.</span></span>
<br><span data-ttu-id="7e9ca-181">![Azure ATP 센서 마법사를 따르려면 다음을 클릭 해야 하는 Advanced Threat Protection 페이지 of_Azure 합니다.](../../media/mtp-eval-48.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-181">![Image of_Azure Advanced Threat Protection page where you should click next to follow the Azure ATP sensor wizard](../../media/mtp-eval-48.png)</span></span> <br>
 
8. <span data-ttu-id="7e9ca-182">마법사의 다음에 입력 하는 데 필요한 대로 액세스 키를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-182">Copy the access key as you will need to enter it next in the Wizard.</span></span>
<span data-ttu-id="7e9ca-183">![다음 Azure ATP 센서 설정 마법사 페이지에 입력 해야 하는 액세스 키를 복사 해야 하는 이미지 of_the 센서 페이지](../../media/mtp-eval-49.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-183">![Image of_the sensors page where you should copy the access key that you need to enter in the next Azure ATP sensor setup wizard page](../../media/mtp-eval-49.png)</span></span> <br>
 
9. <span data-ttu-id="7e9ca-184">Access 키를 마법사에 복사 하 고 **설치**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-184">Copy the access key into the Wizard and click **Install**.</span></span> 
<br><span data-ttu-id="7e9ca-185">![이미지 of_Azure Advanced Threat Protection Azure ATP 센서 마법사 페이지에서 액세스 키를 입력 한 다음 install (설치) 단추를 클릭 합니다.](../../media/mtp-eval-50.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-185">![Image of_Azure Advanced Threat Protection Azure ATP sensor wizard page where you should provide the access key and then click the install button](../../media/mtp-eval-50.png)</span></span> <br>

10. <span data-ttu-id="7e9ca-186">축 하 합니다. 도메인 컨트롤러에서 Azure Advanced Threat Protection을 구성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-186">Congratulations, you have successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>
<span data-ttu-id="7e9ca-187">![이미지 of_Azure Advanced Threat Protection Azure ATP 센서 마법사 설치 완료 (finish) 단추를 클릭 해야 하는 경우](../../media/mtp-eval-51.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-187">![Image of_Azure Advanced Threat Protection Azure ATP sensor wizard installation completion where you should click the finish button](../../media/mtp-eval-51.png)</span></span> <br>
 
11. <span data-ttu-id="7e9ca-188">[Azure AZURE atp](https://go.microsoft.com/fwlink/?linkid=2040449) 설정 섹션에서 **Windows Defender atp**를 선택한 다음 전환 켜기를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn the toggle on.</span></span> <span data-ttu-id="7e9ca-189">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-189">Click **Save**.</span></span> 
<span data-ttu-id="7e9ca-190">![이미지 of_the Azure Azure ATP 설정 페이지 Windows Defender ATP 전환 기능을 설정 해야 합니다.](../../media/mtp-eval-52.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-190">![Image of_the Azure Azure ATP settings page where you should turn the Windows Defender ATP toggle on](../../media/mtp-eval-52.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="7e9ca-191">Windows Defender ATP가 Microsoft Defender ATP와 다시 브랜드 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="7e9ca-192">모든 포털에서 다시 브랜딩 변경을 수행 하는 것은 일관성을 위해 롤업 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="7e9ca-193">Microsoft Cloud App Security 구성</span><span class="sxs-lookup"><span data-stu-id="7e9ca-193">Configure Microsoft Cloud App Security</span></span>
>[!NOTE]
><span data-ttu-id="7e9ca-194">Microsoft Cloud App Security를 이미 사용 하도록 설정한 경우에는이 단계를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-194">Skip this step if you have already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="7e9ca-195">[Microsoft 365 보안 센터로](https://security.microsoft.com/info)이동  >  **More Resources**  >  **microsoft Cloud App security**.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>
<span data-ttu-id="7e9ca-196">![Image of_Microsoft 365 Microsoft Cloud App card를 볼 수 있고 열기 단추를 클릭 해야 하는 보안 센터 페이지](../../media/mtp-eval-53.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-196">![Image of_Microsoft 365 Security Center page where you can see Microsoft Cloud App card and should click the open button](../../media/mtp-eval-53.png)</span></span> <br>

2. <span data-ttu-id="7e9ca-197">Azure ATP를 통합 하는 정보 프롬프트에서 **AZURE atp 데이터 통합 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span> 
<br><span data-ttu-id="7e9ca-198">![Azure ATP 데이터 통합 링크 사용을 선택 해야 하는 Azure ATP 통합을 위한 이미지 of_the 정보 프롬프트](../../media/mtp-eval-54.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-198">![Image of_the information prompt to integrate Azure ATP where you should select the Enable Azure ATP data integration link](../../media/mtp-eval-54.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="7e9ca-199">이 메시지가 표시 되지 않으면 Azure ATP 데이터 통합이 이미 사용 하도록 설정 되었음을 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="7e9ca-200">그러나 확실히 모르는 경우 IT 관리자에 게 문의 하 여 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="7e9ca-201">**설정**으로 이동 하 여 **Azure ATP 통합** 설정/해제를 켠 다음 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-201">Go to **Settings**, turn the **Azure ATP integration** toggle on, then click **Save**.</span></span> 
<span data-ttu-id="7e9ca-202">![Azure ATP 통합 설정/해제를 설정 해야 하는 이미지 of_the 설정 페이지를 표시 하 고 저장을 클릭 합니다.](../../media/mtp-eval-55.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-202">![Image of_the settings page where you should turn the Azure ATP integration toggle on then click save](../../media/mtp-eval-55.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="7e9ca-203">새 Azure ATP 인스턴스의 경우이 통합 토글이 자동으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="7e9ca-204">다음 단계를 진행 하기 전에 Azure ATP 통합을 사용 하도록 설정 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="7e9ca-205">클라우드 검색 설정 아래에서 **Microsoft DEFENDER ATP 통합**을 선택한 다음 통합을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="7e9ca-206">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-206">Click **Save**.</span></span>
<span data-ttu-id="7e9ca-207">![Microsoft defender ATP 통합 아래의 unsanctioned 앱 차단 확인란이 선택 된 Microsoft Defender ATP 페이지 이미지를 of_the 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-207">![Image of_the Microsoft Defender ATP page where the block unsanctioned apps checkbox under Microsoft Defender ATP integration is selected.</span></span> <span data-ttu-id="7e9ca-208">저장을 클릭 합니다.](../../media/mtp-eval-56.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-208">Click save.](../../media/mtp-eval-56.png)</span></span> <br>

5. <span data-ttu-id="7e9ca-209">클라우드 검색 설정에서 **사용자 향상**을 선택한 다음 Azure Active Directory와의 통합을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-209">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>
<span data-ttu-id="7e9ca-210">![Azure Active Directory 사용자 이름으로 검색 된 사용자 식별자가 선택 됨 확인란을 선택한 사용자 향상 섹션 이미지](../../media/mtp-eval-57.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-210">![Image of User enrichment section where the enrich discovered user identifiers with Azure Active Directory usernames checkbox is selected](../../media/mtp-eval-57.png)</span></span> <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="7e9ca-211">Microsoft Defender Advanced Threat Protection 구성</span><span class="sxs-lookup"><span data-stu-id="7e9ca-211">Configure Microsoft Defender Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="7e9ca-212">Microsoft Defender Advanced Threat Protection을 이미 사용 하도록 설정한 경우에는이 단계를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-212">Skip this step if you have already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="7e9ca-213">[Microsoft 365 보안 센터](https://security.microsoft.com/info)  >  **More Resources**  >  **microsoft Defender 보안 센터**리소스로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-213">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="7e9ca-214">**열기**를 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="7e9ca-214">Click **Open**.</span></span>
<br><span data-ttu-id="7e9ca-215">![Microsoft 365 보안 센터 페이지의 이미지 of_Microsoft Defender 보안 센터 옵션](../../media/mtp-eval-58.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-215">![Image of_Microsoft Defender Security Center option in the Microsoft 365 Security Center page](../../media/mtp-eval-58.png)</span></span> <br>
 
2. <span data-ttu-id="7e9ca-216">Microsoft Defender Advanced Threat Protection 마법사를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-216">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="7e9ca-217">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-217">Click **Next**.</span></span> 
<br><span data-ttu-id="7e9ca-218">![이미지 of_the Microsoft Defender 보안 센터 시작 마법사 페이지](../../media/mtp-eval-59.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-218">![Image of_the Microsoft Defender Security Center welcome wizard page](../../media/mtp-eval-59.png)</span></span> <br>

3. <span data-ttu-id="7e9ca-219">기본 설정 데이터 저장소 위치, 데이터 보존 정책, 조직 크기 및 미리 보기 기능의 옵트인에 따라를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-219">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span> 
<br><span data-ttu-id="7e9ca-220">![이미지 of_the 페이지에서 데이터 저장소 국가, 보존 정책 및 조직 크기를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-220">![Image of_the page to select your data storage country, retention policy, and organization size.</span></span> <span data-ttu-id="7e9ca-221">선택이 완료 되 면 다음을 클릭 합니다.](../../media/mtp-eval-60.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-221">Click next when you're done selecting.](../../media/mtp-eval-60.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="7e9ca-222">나중에 데이터 저장 위치와 같은 일부 설정은 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-222">You cannot change some of the settings, like data storage location, afterwards.</span></span> 
<br>

<span data-ttu-id="7e9ca-223">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-223">Click **Next**.</span></span> 

4. <span data-ttu-id="7e9ca-224">**계속** 을 클릭 하 고 MICROSOFT Defender ATP 테 넌 트를 프로 비전 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-224">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>
<br><span data-ttu-id="7e9ca-225">!["계속" 단추를 클릭 하 여 클라우드 인스턴스를 만들도록 하는 이미지 of_the 페이지 프롬프트](../../media/mtp-eval-61.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-225">![Image of_the page prompting you click the continue button to create your cloud instance](../../media/mtp-eval-61.png)</span></span> <br>

5. <span data-ttu-id="7e9ca-226">그룹 정책, Microsoft Endpoint Manager 또는 Microsoft Defender ATP에 대 한 로컬 스크립트를 실행 하 여 끝점을 온보드 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-226">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="7e9ca-227">편의상이 가이드에서는 로컬 스크립트를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-227">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="7e9ca-228">**패키지 다운로드** 를 클릭 하 고 사용자의 끝점에 온 보 딩 스크립트를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-228">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>  
<br><span data-ttu-id="7e9ca-229">![사용자가 끝점 또는 끝점에 온 보 딩 스크립트를 복사할 수 있도록 패키지 다운로드 단추를 클릭 하 라는 메시지를 표시 하는 이미지 of_page](../../media/mtp-eval-62.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-229">![Image of_page prompting you click the Download package button to copy the onboarding script to your endpoint or endpoints](../../media/mtp-eval-62.png)</span></span> <br>

7. <span data-ttu-id="7e9ca-230">끝점에서 온 보 딩 스크립트를 관리자로 실행 하 고 Y를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-230">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span>
<br><span data-ttu-id="7e9ca-231">![온 보 딩 스크립트를 실행 하는 이미지 of_the 명령줄을 선택한 다음 계속 하려면 Y를 선택 합니다.](../../media/mtp-eval-63.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-231">![Image of_the commandline where you run the onboarding script and choose Y to proceed](../../media/mtp-eval-63.png)</span></span> <br>

8. <span data-ttu-id="7e9ca-232">축 하 합니다, 첫 번째 끝점을 등록 했습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-232">Congratulations, you have onboarded your first endpoint.</span></span>  
<br>![첫 번째 끝점을 등록 확인 하는 메시지가 표시 되는 이미지 of_the 명령줄입니다.](../../media/mtp-eval-64.png) <br>

9. <span data-ttu-id="7e9ca-235">Microsoft Defender ATP 마법사의 검색 테스트를 복사 하 여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-235">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>
<br><span data-ttu-id="7e9ca-236">![이미지 of_the 복사를 클릭 하 여 명령 프롬프트에 붙여 넣으려는 검색 테스트 스크립트를 복사 하는 검색 테스트 단계를 실행 합니다.](../../media/mtp-eval-65.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-236">![Image of_the run a detection test step where you should click Copy to copy the detection test script that you should paste in the command prompt](../../media/mtp-eval-65.png)</span></span> <br>

10. <span data-ttu-id="7e9ca-237">관리자 권한 명령 프롬프트에 PowerShell 스크립트를 복사 하 고 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-237">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 
<br><span data-ttu-id="7e9ca-238">![관리자 권한 명령 프롬프트에 PowerShell 스크립트를 복사 하 고 실행 해야 하는 이미지 of_command 프롬프트](../../media/mtp-eval-66.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-238">![Image of_command prompt where you should copy the PowerShell script to an elevated command prompt and run it](../../media/mtp-eval-66.png)</span></span> <br>

11. <span data-ttu-id="7e9ca-239">마법사에서 **Microsoft DEFENDER ATP 사용 시작** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-239">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>
<br><span data-ttu-id="7e9ca-240">![Microsoft Defender ATP 사용 시작을 클릭 해야 하는 마법사의 이미지 of_the 확인 메시지를 표시 합니다.](../../media/mtp-eval-67.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-240">![Image of_the confirmation prompt from the wizard where you should click Start using Microsoft Defender ATP](../../media/mtp-eval-67.png)</span></span> <br>
 
12. <span data-ttu-id="7e9ca-241">[Microsoft Defender 보안 센터](https://securitycenter.windows.com/)를 방문 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-241">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="7e9ca-242">**설정** 으로 이동한 후 **고급 기능**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-242">Go to **Settings** and then select **Advanced features**.</span></span> 
<br><span data-ttu-id="7e9ca-243">![고급 기능을 선택 해야 하는 이미지 of_Microsoft Defender 보안 센터 설정 메뉴](../../media/mtp-eval-68.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-243">![Image of_Microsoft Defender Security Center Settings menu where you should select Advanced features](../../media/mtp-eval-68.png)</span></span> <br>

13. <span data-ttu-id="7e9ca-244">**Azure Advanced Threat Protection**과의 통합을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-244">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  
<br><span data-ttu-id="7e9ca-245">![이미지 of_Microsoft Defender 보안 센터 고급 기능, Azure Advanced Threat Protection 옵션 설정/해제 해야 하는 경우](../../media/mtp-eval-69.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-245">![Image of_Microsoft Defender Security Center Advanced features, Azure Advanced Threat Protection option toggle that you need to turn on](../../media/mtp-eval-69.png)</span></span> <br>

14. <span data-ttu-id="7e9ca-246">**Office 365 위협 인텔리전스**와의 통합을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-246">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>
<br><span data-ttu-id="7e9ca-247">![이미지 of_Microsoft Defender 보안 센터 고급 기능, Office 365 위협 인텔리전스 옵션 설정/해제 해야 하는 경우](../../media/mtp-eval-70.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-247">![Image of_Microsoft Defender Security Center Advanced features, Office 365 Threat Intelligence option toggle that you need to turn on](../../media/mtp-eval-70.png)</span></span> <br>

15. <span data-ttu-id="7e9ca-248">**Microsoft Cloud App Security**와의 통합을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-248">Turn on integration with **Microsoft Cloud App Security**.</span></span>
<br><span data-ttu-id="7e9ca-249">![이미지 of_Microsoft Defender 보안 센터 고급 기능, Microsoft Cloud App Security option 전환에 필요한 기능](../../media/mtp-eval-71.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-249">![Image of_Microsoft Defender Security Center Advanced features, Microsoft Cloud App Security option toggle that you need to turn on](../../media/mtp-eval-71.png)</span></span> <br>

16. <span data-ttu-id="7e9ca-250">아래로 스크롤한 후 **기본 설정 저장** 을 클릭 하 여 새 통합을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-250">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>
<br><span data-ttu-id="7e9ca-251">![클릭 해야 하는 이미지 of_Save 기본 설정 단추](../../media/mtp-eval-72.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-251">![Image of_Save preferences button that you need to click](../../media/mtp-eval-72.png)</span></span> <br>

## <a name="turn-on-microsoft-threat-protection"></a><span data-ttu-id="7e9ca-252">Microsoft Threat Protection 사용 설정</span><span class="sxs-lookup"><span data-stu-id="7e9ca-252">Turn on Microsoft Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="7e9ca-253">2020 년 6 월 1 일부 부터는 Microsoft에서 모든 적격 테 넌 트에 대해 Microsoft Threat Protection 기능을 자동으로 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-253">Starting June 1, 2020, Microsoft automatically enables Microsoft Threat Protection features for all eligible tenants.</span></span> <span data-ttu-id="7e9ca-254">자세한 내용은 [라이선스 자격에 대 한 Microsoft 기술 커뮤니티 문서를](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-254">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 
<br>
1. <span data-ttu-id="7e9ca-255">[Microsoft 365 보안 센터로](https://security.microsoft.com/homepage)이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-255">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="7e9ca-256">**설정** 으로 이동한 후 **Microsoft Threat Protection**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-256">Navigate to **Settings** and then select **Microsoft Threat Protection**.</span></span>
<br><span data-ttu-id="7e9ca-257">![이미지 of_Microsoft 위협 보호 옵션 스크린샷 (Microsoft 365 보안 센터 설정 페이지)](../../media/mtp-eval-72b.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-257">![Image of_Microsoft Threat Protection option screenshot from the Microsoft 365 Security Center Settings page ](../../media/mtp-eval-72b.png)</span></span> <br>

2. <span data-ttu-id="7e9ca-258">**Microsoft Threat Protection 설정** 확인란을 선택 하 고 **저장**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-258">Select the **Turn on Microsoft Threat Protection** checkbox, then click **Save**.</span></span>
<br><span data-ttu-id="7e9ca-259">![이미지 of_Microsoft 위협 보호 옵션 스크린샷 (Microsoft 365 보안 센터 설정 페이지)](../../media/mtp-eval-72c.png)</span><span class="sxs-lookup"><span data-stu-id="7e9ca-259">![Image of_Microsoft Threat Protection option screenshot from the Microsoft 365 Security Center Settings page ](../../media/mtp-eval-72c.png)</span></span> <br>

<span data-ttu-id="7e9ca-260">축하합니다!</span><span class="sxs-lookup"><span data-stu-id="7e9ca-260">Congratulations!</span></span> <span data-ttu-id="7e9ca-261">Microsoft Threat Protection 평가판 테스트 환경을 방금 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-261">You've just created your Microsoft Threat Protection trial lab environment!</span></span> <span data-ttu-id="7e9ca-262">이제 공격을 시뮬레이트하고 외적 기능에서 검색 하는 방법을 확인 하 고, 알림을 생성 하 고, 끝점에서 fileless 공격에 자동으로 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-262">You can now simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7e9ca-263">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7e9ca-263">Next steps</span></span>
<span data-ttu-id="7e9ca-264">[테스트 경고를 생성](generate-test-alert.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7e9ca-264">[Generate a test alert](generate-test-alert.md).</span></span>
