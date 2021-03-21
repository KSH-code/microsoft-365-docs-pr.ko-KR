---
title: 평가판 랩 또는 파일럿 환경에 대한 Microsoft 365 Defender 기조 구성
description: 평가판 랩 또는 파일럿 환경에 대해 Microsoft Defender for Office 365, ID용 Microsoft Defender, Microsoft Cloud App Security 및 끝점용 Microsoft Defender와 같은 Microsoft 365 Defender 기조를 구성합니다.
keywords: Microsoft Threat Protection 평가판 구성, Microsoft Threat Protection 평가판 구성, Microsoft Threat Protection 파일럿 프로젝트 구성, Microsoft Threat Protection 기조 구성, Microsoft Threat Protection 기조
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6b6ff23ef888c167385ad127d3eb0addb66aebc2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929201"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="15966-104">평가판 랩 또는 파일럿 환경에 맞게 Microsoft 365 Defender 기조 구성</span><span class="sxs-lookup"><span data-stu-id="15966-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="15966-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="15966-105">**Applies to:**</span></span>
- <span data-ttu-id="15966-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15966-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="15966-107">Microsoft 365 Defender 평가판 랩 또는 파일럿 환경을 만들고 배포하는 과정은 다음 3단계 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="15966-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="15966-108">[![1단계: 준비](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="15966-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="15966-109">1단계: 준비</span><span class="sxs-lookup"><span data-stu-id="15966-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |<span data-ttu-id="15966-110">[![2단계: 설정](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="15966-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span></span><br/>[<span data-ttu-id="15966-111">2단계: 설정</span><span class="sxs-lookup"><span data-stu-id="15966-111">Phase 2: Set up</span></span>](setup-mtpeval.md) |![3단계: 온보더](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="15966-113">3단계: 온보더</span><span class="sxs-lookup"><span data-stu-id="15966-113">Phase 3: Onboard</span></span> | <span data-ttu-id="15966-114">[![파일럿으로 돌아가기](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="15966-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="15966-115">파일럿 플레이북으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="15966-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="15966-116">*여기 있습니다!*</span><span class="sxs-lookup"><span data-stu-id="15966-116">*You are here!*</span></span> | |

<span data-ttu-id="15966-117">현재 구성 단계에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15966-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="15966-118">성공적인 배포의 핵심은 준비입니다.</span><span class="sxs-lookup"><span data-stu-id="15966-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="15966-119">이 문서에서는 끝점용 Microsoft Defender 배포를 준비할 때 고려해야 할 지점을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="15966-120">Microsoft 365 Defender 기조</span><span class="sxs-lookup"><span data-stu-id="15966-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="15966-121">Microsoft 365 Defender는 4개의 기조로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="15966-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="15966-122">하나의 기둥이 네트워크 조직의 보안에 이미 가치를 제공할 수 있겠지만 네 가지 Microsoft 365 Defender 기조를 사용하도록 설정하면 조직에 가장 큰 가치를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![사용자용 of_Microsoft 365 Defender 솔루션, 끝점용 Microsoft Defender for Endpoint, 클라우드 앱용, Microsoft Cloud App Security 및 데이터용 Microsoft Defender for Office 365용 Microsoft Defender 솔루션](../../media/mtp/m365pillars.png)

<span data-ttu-id="15966-124">이 섹션에서는 다음을 구성하는 방법을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="15966-125">Office 365용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="15966-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="15966-126">ID용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="15966-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="15966-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="15966-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="15966-128">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="15966-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="15966-129">Office 365용 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="15966-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="15966-130">Office 365용 Defender를 이미 사용하도록 설정한 경우 이 단계를 건너뜁.</span><span class="sxs-lookup"><span data-stu-id="15966-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="15966-131">이러한 설정 중 일부를 확인하는 데 도움이 *되는 Office 365 Advanced Threat Protection 권장 구성 분석기(ORCA)라는* PowerShell 모듈이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15966-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="15966-132">테넌트에서 관리자로 실행하면 get-ORCAReport는 스팸 방지, 피싱 방지 및 기타 메시지 예방조치 설정에 대한 평가를 생성하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15966-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="15966-133">이 모듈은 에서 다운로드할 수 https://www.powershellgallery.com/packages/ORCA/ 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15966-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="15966-134">Office [365 보안](https://protection.office.com/homepage)및 & 센터  >  **위협 관리 정책으로**  >  **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="15966-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![이미지 of_Office 365 보안 & 센터 위협 관리 정책 페이지](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="15966-136">피싱 **방지를 클릭하고** **정책** 이름 및 설명 만들기를 선택하고 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="15966-137">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-137">Click **Next**.</span></span>

   ![정책의 이름을 of_Office 365 보안 & 준수 센터 피싱 방지 정책 페이지 이미지](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="15966-139">Microsoft Defender for Office 365에서 고급 피싱 방지 정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="15966-140">고급 **피싱 임계값을** **2 - 적극적으로 변경합니다.**</span><span class="sxs-lookup"><span data-stu-id="15966-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="15966-141">조건 **추가** 드롭다운 메뉴를 클릭하고 받는 사람 도메인으로 도메인을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="15966-142">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-142">Click **Next**.</span></span>

   ![응용 of_Office 조건을 추가할 수 있는 & 365 보안 & 준수 센터 피싱 방지 정책 페이지 이미지](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="15966-144">설정을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-144">Review your settings.</span></span> <span data-ttu-id="15966-145">이 **정책 만들기를 클릭하여** 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15966-145">Click **Create this policy** to confirm.</span></span> 

   ![of_Office 설정을 검토하고 이 정책 만들기 단추를 클릭할 수 있는 & 365 보안 & 준수 센터 피싱 방지 정책 페이지 이미지](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="15966-147">안전한 **첨부 파일을** 선택하고 **SharePoint, OneDrive 및 Microsoft Teams에 대해 ATP 켜기 옵션을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![SharePoint of_Office OneDrive 및 Microsoft Teams의 ATP를 & 수 있는 365 보안 및 준수 센터 페이지 이미지](../../media/mtp-eval-36.png)

6. <span data-ttu-id="15966-149">+ 아이콘을 클릭하여 새 안전한 첨부 파일 정책을 만들고 도메인에 받는 사람 도메인으로 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="15966-150">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-150">Click **Save**.</span></span>

   ![새 of_Office 안전한 첨부 파일 & 만들 수 있는 365 보안 및 준수 센터 페이지 이미지](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="15966-152">그런 다음 안전한 링크 **정책을** 선택한 다음 연필 아이콘을 클릭하여 기본 정책을 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="15966-153">나머지 옵션이  선택되어 있는 동안 사용자가 안전한 링크를 클릭하는 경우 추적 안 하세요. 옵션이 선택되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="15966-154">자세한 [내용은 안전한 링크](../office-365-security/recommended-settings-for-eop-and-office365-atp.md) 설정을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="15966-154">See [Safe Links settings](../office-365-security/recommended-settings-for-eop-and-office365-atp.md) for details.</span></span> <span data-ttu-id="15966-155">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-155">Click **Save**.</span></span> 

   ![이미지 of_Office 365 보안 & 준수 센터 페이지에서 사용자가 안전을 클릭하는 경우 추적 안 하도록 설정 옵션이 선택되어 있지 않습니다.](../../media/mtp-eval-38.png)

9. <span data-ttu-id="15966-157">그런 다음 **맬웨어** 방지 정책을 선택하고 기본값을 선택하고 연필 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="15966-158">설정을 **클릭하고** **예를 선택하고** 기본 알림 텍스트를 사용하여 맬웨어 검색 **응답을 사용하도록 설정할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="15966-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="15966-159">일반 첨부 **파일 형식 필터를 켜습니다.**</span><span class="sxs-lookup"><span data-stu-id="15966-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="15966-160">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-160">Click **Save**.</span></span>

    ![기본 of_Office 알림과 함께 맬웨어 검색 응답이 켜져 있으며 일반적인 첨부 파일 형식 필터가 켜져 있는 & 365 보안 및 준수 센터 페이지 이미지](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="15966-162">Office [365 보안](https://protection.office.com/homepage)및 준수 & 감사 로그 검색으로  >    >  **이동한** 다음 감사를 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![감사 of_Office 365 보안 & 센터 페이지에서 감사 로그 검색을 켜면 됩니다.](../../media/mtp-eval-40.png)

12. <span data-ttu-id="15966-164">Office 365용 Microsoft Defender를 끝점용 Microsoft Defender와 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="15966-165">Office [365 보안](https://protection.office.com/homepage)& 준수 센터 위협 관리 탐색기로 이동하고 화면 오른쪽 위 모서리에서  >    >   끝점 설정에 대한 **Microsoft Defender를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="15966-166">끝점 연결용 Defender 대화 상자에서 **끝점용 Microsoft Defender에 연결을 켜야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="15966-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![끝점 of_Office Microsoft Defender를 끄는 & 365 보안 및 준수 센터 페이지 이미지](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="15966-168">ID에 맞게 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="15966-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="15966-169">Id에 대해 Microsoft Defender를 이미 사용하도록 설정한 경우 이 단계를 건너뛰기</span><span class="sxs-lookup"><span data-stu-id="15966-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="15966-170">Microsoft [365](https://security.microsoft.com/info) 보안 센터로 이동하여 >  >  **추가 리소스를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="15966-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Id에 대한 Microsoft Defender를 여는 옵션이 있는 of_Microsoft 365 보안 센터 페이지 이미지](../../media/mtp-eval-42.png)

2. <span data-ttu-id="15966-172">**만들기를** 클릭하여 Id에 대한 Microsoft Defender 마법사를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![만들기 of_Microsoft 클릭해야 하는 ID용 Defender 마법사 페이지 이미지](../../media/mtp-eval-43.png)

3. <span data-ttu-id="15966-174">사용자 이름 및 암호 제공을 선택하고 Active Directory 포리스트에 **연결합니다.**</span><span class="sxs-lookup"><span data-stu-id="15966-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![ID of_Microsoft Defender 이미지 페이지](../../media/mtp-eval-44.png)

4. <span data-ttu-id="15966-176">Active Directory의 사내 자격 증명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="15966-177">이 계정은 Active Directory에 대한 읽기 권한이 있는 모든 사용자 계정일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15966-177">This can be any user account that has read access to Active Directory.</span></span>

   ![자격 증명을 of_Microsoft Id 디렉터리 서비스 페이지에 대한 Defender 이미지](../../media/mtp-eval-45.png)

5. <span data-ttu-id="15966-179">그런 다음 센서 설치 **다운로드를 선택하고** 파일을 도메인 컨트롤러로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![센서 of_Microsoft 다운로드를 선택할 수 있는 ID용 Defender 이미지 페이지](../../media/mtp-eval-46.png)

6. <span data-ttu-id="15966-181">Microsoft Defender for Identity Sensor Setup을 실행하고 마법사 다음을 시작하십시오.</span><span class="sxs-lookup"><span data-stu-id="15966-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![ID of_Microsoft Microsoft Defender 센서 마법사를 따라 이동하려면 다음을 클릭해야 하는 ID용 Defender 페이지 이미지](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="15966-183">센서 **배포 유형에서** 다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-183">Click **Next** at the sensor deployment type.</span></span>

   ![다음 of_Microsoft 이동하려면 다음을 클릭해야 하는 ID용 Defender 페이지 이미지](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="15966-185">마법사에서 다음에 입력해야 하여 액세스 키를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![이미지 of_the 다음 Microsoft Defender for Identity 센서 설정 마법사 페이지에 입력해야 하는 액세스 키를 복사해야 하는 센서 페이지](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="15966-187">마법사에 선택키를 복사하고 설치를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="15966-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![선택키를 of_Microsoft 설치 단추를 클릭해야 하는 ID용 Defender 센서 마법사 페이지에 대한 이미지](../../media/mtp-eval-50.png)

10. <span data-ttu-id="15966-189">축하합니다. 도메인 컨트롤러에서 ID에 대한 Microsoft Defender를 성공적으로 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="15966-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![완료 of_Microsoft 클릭해야 하는 ID용 Defender 센서 마법사 설치 완료 이미지](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="15966-191">Id [설정에 대한 Microsoft Defender 섹션에서](https://go.microsoft.com/fwlink/?linkid=2040449) \*\*끝점용 Microsoft Defender \*\*를 선택한 다음 토글을 켜십시오.</span><span class="sxs-lookup"><span data-stu-id="15966-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="15966-192">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-192">Click **Save**.</span></span> 

    ![끝점 of_the Microsoft Defender 토글을 켜야 하는 ID용 Microsoft Defender 설정 페이지의 이미지](../../media/mtp-eval-52.png)

> [!NOTE]
> <span data-ttu-id="15966-194">Windows Defender ATP는 끝점용 Microsoft Defender로 다시 브랜드가 업데이트되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15966-194">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="15966-195">일관성을 위해 모든 포털에서 변경 내용을 변경하는 것이 롤아웃되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15966-195">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="15966-196">Microsoft Cloud App Security 구성</span><span class="sxs-lookup"><span data-stu-id="15966-196">Configure Microsoft Cloud App Security</span></span>

> [!NOTE]
> <span data-ttu-id="15966-197">Microsoft Cloud App Security를 이미 사용하도록 설정한 경우 이 단계를 건너뜁.</span><span class="sxs-lookup"><span data-stu-id="15966-197">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="15966-198">Microsoft [365 보안](https://security.microsoft.com/info)센터 추가  >  **리소스**  >  **Microsoft Cloud App Security로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="15966-198">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![이미지 of_Microsoft Microsoft Cloud App 카드를 볼 수 있으며 열기 단추를 클릭해야 하는 365 보안 센터 페이지](../../media/mtp-eval-53.png)

2. <span data-ttu-id="15966-200">ID에 대한 Microsoft Defender를 통합하기 위한 정보 프롬프트에서 ID 데이터 **통합에 대해 Microsoft Defender 사용 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="15966-200">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![ID에 of_the Microsoft Defender를 통합하기 위한 정보 프롬프트 이미지](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="15966-202">이 프롬프트가 표시되지 않는 경우 ID용 Microsoft Defender 데이터 통합이 이미 활성화되어 있는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15966-202">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="15966-203">그러나 확실하지 않은 경우 IT 관리자에게 문의하여 확인을 합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-203">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="15966-204">설정으로 **이동하여** ID에 대한 **Microsoft Defender 통합** 토글을 켜고 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="15966-204">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![Id에 of_the Microsoft Defender 통합 토글을 켜고 저장을 클릭해야 하는 이미지 설정 페이지](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="15966-206">새 Microsoft Defender for Identity 인스턴스의 경우 이 통합 토글이 자동으로 켜집니다.</span><span class="sxs-lookup"><span data-stu-id="15966-206">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="15966-207">다음 단계를 진행하기 전에 ID에 대한 Microsoft Defender 통합이 활성화되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-207">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="15966-208">클라우드 검색 설정에서 **끝점 통합용 Microsoft Defender를 선택한** 다음 통합을 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="15966-208">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="15966-209">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-209">Click **Save**.</span></span>

   ![이미지 of_the Microsoft Defender for Endpoint 통합 아래에서 차단되지 않은 앱 차단 확인란이 선택된 끝점용 Microsoft Defender 페이지입니다.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="15966-212">클라우드 검색 설정에서 사용자 **강화를 선택한** 다음 Azure Active Directory와의 통합을 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="15966-212">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Azure Active Directory 사용자 이름을 사용하여 검색된 사용자 식별자를 강화 확인란이 선택된 사용자 강화 섹션의 이미지](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="15966-214">끝점에 맞게 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="15966-214">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="15966-215">끝점에 대해 Microsoft Defender를 이미 사용하도록 설정한 경우 이 단계를 건너뜁.</span><span class="sxs-lookup"><span data-stu-id="15966-215">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="15966-216">Microsoft [365 보안](https://security.microsoft.com/info)센터 추가  >  **리소스**  >  **Microsoft Defender 보안 센터로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="15966-216">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="15966-217">**열기** 를 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="15966-217">Click **Open**.</span></span>

   ![Microsoft of_Microsoft 센터 페이지의 이미지 of_Microsoft Defender 보안 센터 옵션](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="15966-219">끝점용 Microsoft Defender 마법사를 따르기.</span><span class="sxs-lookup"><span data-stu-id="15966-219">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="15966-220">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-220">Click **Next**.</span></span> 

   ![Microsoft Defender of_the 시작 마법사 페이지 이미지](../../media/mtp-eval-59.png)

3. <span data-ttu-id="15966-222">기본 설정 데이터 저장소 위치, 데이터 보존 정책, 조직 크기 및 미리 보기 기능에 대한 옵트인(opt in)을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-222">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![이미지 of_the 데이터 저장소 국가, 보존 정책 및 조직 크기를 선택합니다.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="15966-225">데이터 저장 위치와 같은 일부 설정은 이후에 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="15966-225">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="15966-226">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-226">Click **Next**.</span></span> 

4. <span data-ttu-id="15966-227">**계속을** 클릭하면 끝점 테넌트에 대한 Microsoft Defender를 프로비전합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-227">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![클라우드 of_the 만들기 위한 계속 단추를 클릭하라는 메시지 표시 페이지 이미지](../../media/mtp-eval-61.png)

5. <span data-ttu-id="15966-229">그룹 정책, Microsoft 끝점 관리자를 통해 또는 끝점용 Microsoft Defender에 대한 로컬 스크립트를 실행하여 끝점을 온보딩합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-229">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="15966-230">간편한 설명을 위해 이 가이드에서는 로컬 스크립트를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="15966-230">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="15966-231">패키지 **다운로드를** 클릭하고 끝점에 온보딩 스크립트를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-231">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![이미지 of_page 패키지 다운로드 단추를 클릭하여 끝점 또는 끝점에 온보딩 스크립트를 복사합니다.](../../media/mtp-eval-62.png)

7. <span data-ttu-id="15966-233">끝점에서 관리자 권한으로 온보딩 스크립트를 실행하고 Y를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-233">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![이미지 of_the 명령줄에서 온보딩 스크립트를 실행하고 Y를 선택해 계속 진행](../../media/mtp-eval-63.png)

8. <span data-ttu-id="15966-235">축하합니다. 첫 번째 끝점을 온보드했습니다.</span><span class="sxs-lookup"><span data-stu-id="15966-235">Congratulations, you've onboarded your first endpoint.</span></span>

   ![이미지 of_the 끝점을 온보드했다는 확인 메시지가 표시됩니다.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="15966-238">Microsoft Defender for Endpoint 마법사에서 검색 테스트를 복사하여 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="15966-238">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![이미지 of_the 명령 프롬프트에 붙여넣을 검색 테스트 스크립트를 복사하려면 복사를 클릭해야 하는 검색 테스트 단계를 실행합니다.](../../media/mtp-eval-65.png)

10. <span data-ttu-id="15966-240">PowerShell 스크립트를 상승된 명령 프롬프트에 복사하여 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-240">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![PowerShell 스크립트를 of_command 명령 프롬프트에 복사하고 실행해야 하는 이미지 프롬프트](../../media/mtp-eval-66.png)

11. <span data-ttu-id="15966-242">**마법사에서 끝점용 Microsoft Defender 사용** 시작을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-242">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![이미지 of_the 끝점용 Microsoft Defender 사용 시작을 클릭해야 하는 마법사의 확인 프롬프트](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="15966-244">Microsoft [Defender 보안 센터를 방문합니다.](https://securitycenter.windows.com/)</span><span class="sxs-lookup"><span data-stu-id="15966-244">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="15966-245">설정으로 **이동한** 다음 고급 **기능을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="15966-245">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![고급 of_Microsoft 선택해야 하는 Defender 보안 센터 설정 메뉴의 이미지](../../media/mtp-eval-68.png)

13. <span data-ttu-id="15966-247">Id에 대한 **Microsoft Defender와의 통합을 켜기.**</span><span class="sxs-lookup"><span data-stu-id="15966-247">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![이미지 of_Microsoft Defender 보안 센터 고급 기능, ID에 대한 Microsoft Defender 옵션 토글](../../media/mtp-eval-69.png)

14. <span data-ttu-id="15966-249">**Office 365 위협 인텔리전스와의 통합을 켜기**</span><span class="sxs-lookup"><span data-stu-id="15966-249">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![이미지 of_Microsoft Defender 보안 센터 고급 기능, 켜야 하는 Office 365 위협 인텔리전스 옵션 토글](../../media/mtp-eval-70.png)

15. <span data-ttu-id="15966-251">Microsoft Cloud **App Security와의 통합 켜기.**</span><span class="sxs-lookup"><span data-stu-id="15966-251">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![이미지 of_Microsoft Defender 보안 센터 고급 기능, 켜야 하는 Microsoft Cloud App Security 옵션 토글](../../media/mtp-eval-71.png)

16. <span data-ttu-id="15966-253">아래로 스크롤하여 기본 설정 저장을 **클릭하여** 새 통합을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15966-253">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![클릭해야 of_Save 기본 설정 단추 이미지](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="15966-255">Microsoft 365 Defender 서비스 시작</span><span class="sxs-lookup"><span data-stu-id="15966-255">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="15966-256">2020년 6월 1일부터 Microsoft는 모든 적격 테넌트에 대해 Microsoft 365 Defender 기능을 자동으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15966-256">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="15966-257">자세한 내용은 [라이선스 자격에](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) 대한 Microsoft 기술 커뮤니티 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="15966-257">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="15966-258">Microsoft [365 보안 센터로 이동](https://security.microsoft.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="15966-258">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="15966-259">설정으로 **이동한** 다음 **Microsoft 365 Defender 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="15966-259">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="15966-260">Microsoft of_Microsoft 365 보안 센터 설정 페이지의 이미지 365 Defender 옵션 스크린샷</span><span class="sxs-lookup"><span data-stu-id="15966-260">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="15966-261">보다 포괄적인 지침은 [Microsoft 365 Defender 켜기 를 참조하세요.](mtp-enable.md)</span><span class="sxs-lookup"><span data-stu-id="15966-261">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](mtp-enable.md).</span></span> 

<span data-ttu-id="15966-262">축하합니다!</span><span class="sxs-lookup"><span data-stu-id="15966-262">Congratulations!</span></span> <span data-ttu-id="15966-263">방금 Microsoft 365 Defender 평가판 랩 또는 파일럿 환경을 만들게 되었습니다!</span><span class="sxs-lookup"><span data-stu-id="15966-263">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="15966-264">이제 Microsoft 365 Defender 사용자 인터페이스에 익숙해지세요!</span><span class="sxs-lookup"><span data-stu-id="15966-264">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="15966-265">다음 Microsoft 365 Defender 대화형 가이드에서 학습할 수 있는 내용을 알아보고 매일 수행되는 보안 작업 작업에 각 대시보드를 사용하는 방법을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15966-265">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="15966-266">다음으로, 공격을 시뮬레이트하고 제품 간 기능이 끝점에 대한 파일 없는 공격을 감지하고, 경고를 만들고, 자동으로 대응하는 방법을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15966-266">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="15966-267">다음 단계</span><span class="sxs-lookup"><span data-stu-id="15966-267">Next step</span></span>

- <span data-ttu-id="15966-268">[테스트 경고 생성](generate-test-alert.md) - Microsoft 365 Defender 평가판 랩에서 공격 시뮬레이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="15966-268">[Generate a test alert](generate-test-alert.md) - Run an attack simulation in your Microsoft 365 Defender trial lab.</span></span>