---
title: Microsoft 365 Defender 평가판 랩 또는 파일럿 환경 설정
description: Microsoft 365 보안 센터에 액세스한 다음 Microsoft 365 Defender 평가판 랩 환경 설정
keywords: Microsoft Threat Protection 평가판 설정, Microsoft Threat Protection 파일럿 설정, Microsoft Threat Protection 체험, Microsoft Threat Protection 평가 랩 설정
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 835adc5c2bf9fd1c9a14c2d53b17a032a89a6240
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932985"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="68e45-104">Microsoft 365 Defender 평가판 랩 환경 설정</span><span class="sxs-lookup"><span data-stu-id="68e45-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="68e45-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="68e45-105">**Applies to:**</span></span>
- <span data-ttu-id="68e45-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="68e45-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="68e45-107">Microsoft 365 Defender 평가판 랩 또는 파일럿 환경을 만들고 배포하는 과정은 3단계 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="68e45-108">[![1단계: 준비](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="68e45-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="68e45-109">1단계: 준비</span><span class="sxs-lookup"><span data-stu-id="68e45-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |![2단계: 설정](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="68e45-111">2단계: 설정</span><span class="sxs-lookup"><span data-stu-id="68e45-111">Phase 2: Set up</span></span> |<span data-ttu-id="68e45-112">[![3단계: 온보드](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="68e45-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span></span><br/>[<span data-ttu-id="68e45-113">3단계: 온보드</span><span class="sxs-lookup"><span data-stu-id="68e45-113">Phase 3: Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="68e45-114">[![파일럿으로 돌아가기](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="68e45-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="68e45-115">파일럿 플레이북으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="68e45-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="68e45-116">*You are here!*</span><span class="sxs-lookup"><span data-stu-id="68e45-116">*You are here!*</span></span>  | | |


<span data-ttu-id="68e45-117">현재 설정 단계에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-117">You're currently in the set up phase.</span></span> <span data-ttu-id="68e45-118">초기 단계를 수행하여 Microsoft 365 보안 센터에 액세스한 다음 시험 랩 또는 파일럿 환경을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="68e45-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="68e45-119">Office 365 또는 Azure Active Directory 구독에 등록하여 Microsoft 365 E5 *라이선스에 등록하는 데 사용할 수 있는 .onmicrosoft.com* 테넌트 생성</span><span class="sxs-lookup"><span data-stu-id="68e45-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="68e45-120">기존 Office 365 또는 Azure Active Directory 구독이 이미 있는 경우 Office 365 E5 평가판 또는 파일럿 테넌트 만들기 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="68e45-121">이 단계에서는 다음을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="68e45-122">Office 365 E5 평가판 테넌트 만들기</span><span class="sxs-lookup"><span data-stu-id="68e45-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="68e45-123">Microsoft 365 평가판 구독 사용</span><span class="sxs-lookup"><span data-stu-id="68e45-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="68e45-124">Office 365 E5 평가판 테넌트 만들기</span><span class="sxs-lookup"><span data-stu-id="68e45-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="68e45-125">기존 Office 365 또는 Azure Active Directory 구독이 이미 있는 경우 Office 365 E5 평가판 테넌트 만들기 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="68e45-126">[Office 365 E5](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) 제품 포털로 이동하고 무료 **평가판을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e45-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![이미지 of_Office 365 E5 무료 평가판 페이지](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="68e45-128">전자 메일 주소(개인 또는 회사)를 입력하여 평가판 등록을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="68e45-129">계정 **설정을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e45-129">Click **Set up account**.</span></span>

   ![이미지 of_Office 365 E5 평가판 등록 설정 페이지](../../media/mtp-eval-10.png)

3. <span data-ttu-id="68e45-131">이름, 성, 회사 전화 번호, 회사 이름, 회사 규모, 국가 또는 지역을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![이름of_Office 전화 및 회사 세부 정보를 묻는 이미지 365 E5 평가판 등록 설정 페이지](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="68e45-133">여기서 설정한 국가 또는 지역은 Office 365가 호스팅되는 데이터 센터 지역을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="68e45-134">확인 기본 설정(문자 메시지 또는 전화를 통해)을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="68e45-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="68e45-135">확인 **코드 보내기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e45-135">Click **Send Verification Code**.</span></span> 

   ![확인 of_Office 묻는 이미지 365 E5 평가판 등록 설정 페이지](../../media/mtp-eval-12.png)

5. <span data-ttu-id="68e45-137">테넌트의 사용자 지정 도메인 이름을 설정하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e45-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![사용자 지정 of_Office 설정할 수 있는 이미지 365 E5 평가판 등록 설정 페이지](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="68e45-139">테넌트에 대한 전역 관리자가 될 첫 번째 ID를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="68e45-140">이름과 **암호를** **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e45-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="68e45-141">**로그인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-141">Click **Sign up**.</span></span>

   ![비즈니스 of_Office 설정할 수 있는 이미지 365 E5 평가판 등록 설정 페이지](../../media/mtp-eval-14.png)

7. <span data-ttu-id="68e45-143">설치로 **이동을 클릭하여** Office 365 E5 평가판 테넌트 프로비전을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![설치 이동 단추를 클릭하라는 Office 365 E5 평가판 등록 설정 페이지의 이미지](../../media/mtp-eval-15.png)

8. <span data-ttu-id="68e45-145">회사 도메인을 Office 365 테넌트에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="68e45-146">[선택 사항] Choose **Connect a domain you already own** and type in your domain name.</span><span class="sxs-lookup"><span data-stu-id="68e45-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="68e45-147">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-147">Click **Next**.</span></span>

   ![로그인 of_Office 전자 메일을 개인 설정해야 하는 365 E5 설치 페이지 이미지](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="68e45-149">도메인 소유권의 유효성을 검사하려면 TXT 또는 MX 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="68e45-150">도메인에 TXT 또는 MX 레코드를 추가한 후 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e45-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![도메인을 확인하기 위해 MX 레코드의 TXT를 추가해야 하는 이미지 of_Office 365 E5 설치 페이지](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="68e45-152">[선택 사항] 테넌트에 대한 사용자 계정을 더 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="68e45-153">다음을 클릭하여 이 단계를 건너뛸 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="68e45-153">You can skip this step by clicking **Next**.</span></span>

    ![더 많은 of_Office 수 있는 이미지 365 E5 설치 페이지](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="68e45-155">[선택 사항] Office 앱을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="68e45-156">다음을 **클릭하여** 이 단계를 건너뜁습니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-156">Click **Next** to skip this step.</span></span> 

    ![Office of_Office 설치할 수 있는 이미지 365 E5 페이지](../../media/mtp-eval-19.png)

12. <span data-ttu-id="68e45-158">[선택 사항] 전자 메일 메시지를 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="68e45-159">이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-159">Again, you can skip this step.</span></span>

    ![전자 메일 of_Office 마이그레이션할지 여부를 설정할 수 있는 이미지 365 E5](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="68e45-161">온라인 서비스를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="68e45-161">Choose online services.</span></span> <span data-ttu-id="68e45-162">Exchange를 **선택하고** 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e45-162">Select **Exchange** and click **Next**.</span></span> 

    ![온라인 of_Office 선택할 수 있는 이미지 365 E5](../../media/mtp-eval-21.png)

14. <span data-ttu-id="68e45-164">도메인에 MX, CNAME 및 TXT 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="68e45-165">완료되면 확인을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e45-165">When completed, select **Verify**.</span></span>

    ![여기에서 of_Office 365 E5를 사용하여 DNS 레코드를 추가할 수 있습니다.](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="68e45-167">축하합니다. Office 365 테넌트의 프로비전을 완료했습니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![이미지 of_Office 365 E5 설치 완료 확인 페이지](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="68e45-169">Microsoft 365 평가판 구독 사용</span><span class="sxs-lookup"><span data-stu-id="68e45-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="68e45-170">평가판에 등록하면 한 달 동안 사용할 25개 사용자 라이선스가 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="68e45-171">자세한 [내용은 M365](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) 구독 시도 또는 구입을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="68e45-171">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="68e45-172">[Microsoft 365 관리 센터에서](https://admin.microsoft.com/)청구를 클릭한 다음 서비스 **구매로 이동합니다.** </span><span class="sxs-lookup"><span data-stu-id="68e45-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="68e45-173">**Microsoft 365 E5를 선택하고** **평가판 시작을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e45-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![이미지 of_Microsoft 365 E5 무료 평가판 시작 페이지](../../media/mtp-eval-24.png)

3. <span data-ttu-id="68e45-175">확인 기본 설정(문자 메시지 또는 전화를 통해)을 선택하십시오.</span><span class="sxs-lookup"><span data-stu-id="68e45-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="68e45-176">결정한 후 전화 번호를 입력하고  선택에  따라 문자 메시지 또는 전화 걸기를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![이미지 of_Microsoft 365 E5 무료 평가판 시작 페이지에서 로봇이 아 아니라는 것을 증명하기 위해 코드를 보내기 위한 연락처 세부 정보를 요청하는 무료 평가판 페이지](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="68e45-178">인증 코드를 입력하고 무료 **평가판 시작을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e45-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![이미지 of_Microsoft 365 E5 무료 평가판 시작 페이지에서 시스템이 로봇이 아 아니라는 것을 증명하기 위해 전송된 검증 코드를 입력할 수 있습니다.](../../media/mtp-eval-26.png)

5. <span data-ttu-id="68e45-180">지금 **사용해 보시고** Microsoft 365 E5 평가판을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="68e45-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![이미지 of_Microsoft 365 E5 무료 평가판 시작 페이지에서 지금 체험 단추를 시작해야 합니다.](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="68e45-182">**Microsoft 365 관리** 센터 사용자 활성  >    >  **사용자로 이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="68e45-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="68e45-183">사용자 계정을 선택하고 제품 라이선스 관리를 선택한 다음 Office 365 E5에서 **Microsoft 365 E5로** 라이선스를 교체합니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="68e45-184">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-184">Click **Save**.</span></span>

   ![Microsoft of_Microsoft 365 E5 라이선스를 선택할 수 있는 365 관리 센터 페이지 이미지](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="68e45-186">전역 관리자 계정을 다시 선택한 다음 사용자 이름 **관리를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="68e45-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![이미지를 of_Microsoft 365 관리 센터 페이지에서 계정을 선택한 다음 사용자 이름을 관리할 수 있습니다.](../../media/mtp-eval-29.png)

8. <span data-ttu-id="68e45-188">[선택 사항] 이전 단계에서  onmicrosoft.com 따라 도메인을 사용자 도메인으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="68e45-189">**변경 사항 저장** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-189">Click **Save changes**.</span></span>

   ![도메인 of_Microsoft 변경할 수 있는 365 관리 센터 페이지 이미지](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="68e45-191">다음 단계</span><span class="sxs-lookup"><span data-stu-id="68e45-191">Next step</span></span>
|[<span data-ttu-id="68e45-192">3단계: 온보드 & 구성</span><span class="sxs-lookup"><span data-stu-id="68e45-192">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="68e45-193">Microsoft 365 Defender 평가판 랩 또는 파일럿 환경에 대해 각 Microsoft 365 Defender 기조를 구성하고 끝점을 온보딩합니다.</span><span class="sxs-lookup"><span data-stu-id="68e45-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
