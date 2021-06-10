---
title: Microsoft 365 평가판 랩 또는 파일럿 환경 설정
description: Access Microsoft 365 보안 센터에 액세스한 다음 Microsoft 365 Defender 평가판 랩 환경을 설정
keywords: Microsoft 365 Defender 평가판 설치, Microsoft 365 Defender 파일럿 설정, Defender Microsoft 365 평가 Microsoft 365 테스트
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ae81f6be0a83d5d0141f0f0c8c89f8f2207cc56c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935428"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="0a924-104">Defender Microsoft 365 랩 환경 설정</span><span class="sxs-lookup"><span data-stu-id="0a924-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="0a924-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="0a924-105">**Applies to:**</span></span>
- <span data-ttu-id="0a924-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0a924-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="0a924-107">Microsoft 365 테스트 랩 또는 파일럿 환경을 만들고 배포하는 과정은 다음 3단계 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="0a924-108">[![1 단계: 준비](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="0a924-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="0a924-109">1 단계: 준비</span><span class="sxs-lookup"><span data-stu-id="0a924-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |![2 단계: 설정](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="0a924-111">2 단계: 설정</span><span class="sxs-lookup"><span data-stu-id="0a924-111">Phase 2: Set up</span></span> |<span data-ttu-id="0a924-112">[![3 단계: 온보딩](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="0a924-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)</span></span><br/>[<span data-ttu-id="0a924-113">3 단계: 온보딩</span><span class="sxs-lookup"><span data-stu-id="0a924-113">Phase 3: Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="0a924-114">[![파일럿으로 돌아가기](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="0a924-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="0a924-115">파일럿 플레이북으로 돌아가기</span><span class="sxs-lookup"><span data-stu-id="0a924-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="0a924-116">*여기 있습니다!*</span><span class="sxs-lookup"><span data-stu-id="0a924-116">*You are here!*</span></span>  | | |


<span data-ttu-id="0a924-117">현재 설정 단계에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-117">You're currently in the set up phase.</span></span> <span data-ttu-id="0a924-118">보안 센터에 액세스하기 위한 초기 Microsoft 365 테스트 랩 또는 파일럿 환경을 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="0a924-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="0a924-119">Office 365 또는 Azure Active Directory 구독에 등록하여 onmicrosoft.com 라이선스에 등록하는 데 사용할 수 있는 *.onmicrosoft.com* 테넌트 Microsoft 365 E5 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="0a924-120">기존 Office 365 또는 Azure Active Directory 있는 경우 E5 평가판 또는 Office 365 테넌트 만들기 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="0a924-121">이 단계에서는 다음을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="0a924-122">E5 Office 365 테넌트 만들기</span><span class="sxs-lookup"><span data-stu-id="0a924-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="0a924-123">평가판 Microsoft 365 사용</span><span class="sxs-lookup"><span data-stu-id="0a924-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="0a924-124">E5 Office 365 테넌트 만들기</span><span class="sxs-lookup"><span data-stu-id="0a924-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="0a924-125">기존 Office 365 또는 Azure Active Directory 있는 경우 E5 평가판 테넌트 Office 365 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="0a924-126">E5 [Office 365 포털로 이동하고](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) **무료 평가판 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a924-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![이미지 of_Office 365 E5 무료 평가판 페이지](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="0a924-128">전자 메일 주소(개인 또는 회사)를 입력하여 평가판 등록을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="0a924-129">계정 **설정 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a924-129">Click **Set up account**.</span></span>

   ![이미지 of_Office 365 E5 평가판 등록 설정 페이지](../../media/mtp-eval-10.png)

3. <span data-ttu-id="0a924-131">이름, 성, 회사 전화 번호, 회사 이름, 회사 크기, 국가 또는 지역을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![이름of_Office 전화 및 회사 세부 정보를 요청하는 365 E5 평가판 등록 설정 페이지 이미지](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="0a924-133">여기서 설정한 국가 또는 지역은 호스트할 데이터 센터 Office 365 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="0a924-134">확인 기본 설정 선택: 문자 메시지 또는 전화를 통해 선택</span><span class="sxs-lookup"><span data-stu-id="0a924-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="0a924-135">확인 **코드 보내기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a924-135">Click **Send Verification Code**.</span></span> 

   ![확인 of_Office 묻는 365 E5 평가판 등록 설정 페이지 이미지](../../media/mtp-eval-12.png)

5. <span data-ttu-id="0a924-137">테넌트에 대한 사용자 지정 도메인 이름을 설정하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a924-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![사용자 of_Office 설정할 수 있는 365 E5 평가판 등록 설정 페이지 이미지](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="0a924-139">테넌트의 전역 관리자가 될 첫 번째 ID를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="0a924-140">이름 및 **암호를** **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a924-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="0a924-141">**로그인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-141">Click **Sign up**.</span></span>

   ![비즈니스 of_Office 설정할 수 있는 365 E5 평가판 등록 설정 페이지 이미지](../../media/mtp-eval-14.png)

7. <span data-ttu-id="0a924-143">설치로 **이동을 클릭하여** Office 365 테넌트 프로비전을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![설치 Office 365 클릭하라는 메시지를 표시하는 E5 평가판 등록 설정 페이지의 이미지](../../media/mtp-eval-15.png)

8. <span data-ttu-id="0a924-145">커넥트 도메인을 Office 365 테넌트에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="0a924-146">[선택 사항] 이미 **커넥트** 도메인을 선택하고 도메인 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="0a924-147">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-147">Click **Next**.</span></span>

   ![로그인 of_Office 전자 메일을 개인 설정해야 하는 365 E5 설치 페이지 이미지](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="0a924-149">TXT 또는 MX 레코드를 추가하여 도메인 소유권의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="0a924-150">도메인에 TXT 또는 MX 레코드를 추가한 후 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a924-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![도메인을 of_Office MX 레코드의 TXT를 추가해야 하는 365 E5 설치 페이지 이미지](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="0a924-152">[선택 사항] 테넌트에 대한 사용자 계정을 더 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="0a924-153">다음 을 클릭하여 이 단계를 건너뛸 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="0a924-153">You can skip this step by clicking **Next**.</span></span>

    ![더 of_Office 추가할 수 있는 365 E5 설치 페이지 이미지](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="0a924-155">[선택 사항] 앱 Office 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="0a924-156">이 **단계를** 건너뛰려면 다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-156">Click **Next** to skip this step.</span></span> 

    ![of_Office 앱을 설치할 수 있는 365 E5 Office 이미지](../../media/mtp-eval-19.png)

12. <span data-ttu-id="0a924-158">[선택 사항] 전자 메일 메시지를 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="0a924-159">이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-159">Again, you can skip this step.</span></span>

    ![전자 of_Office 마이그레이션할지 여부를 설정할 수 있는 365 E5 이미지](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="0a924-161">온라인 서비스를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="0a924-161">Choose online services.</span></span> <span data-ttu-id="0a924-162">다음 **Exchange** 선택하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a924-162">Select **Exchange** and click **Next**.</span></span> 

    ![온라인 of_Office 선택할 수 있는 365 E5 이미지](../../media/mtp-eval-21.png)

14. <span data-ttu-id="0a924-164">도메인에 MX, CNAME 및 TXT 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="0a924-165">완료되면 확인 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a924-165">When completed, select **Verify**.</span></span>

    ![여기에서 of_Office 365 E5를 사용하여 DNS 레코드를 추가할 수 있습니다.](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="0a924-167">축하합니다. 사용자 테넌트의 프로비전을 Office 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![이미지 of_Office 365 E5 설치 완료 확인 페이지](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="0a924-169">평가판 Microsoft 365 사용</span><span class="sxs-lookup"><span data-stu-id="0a924-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="0a924-170">평가판에 등록하면 한 달 동안 사용할 25개 사용자 라이선스가 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="0a924-171">자세한 [내용은 M365](../../commerce/try-or-buy-microsoft-365.md) 구독 시도 또는 구입을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a924-171">See [Try or Buy an M365 subscription](../../commerce/try-or-buy-microsoft-365.md) for details.</span></span>

1. <span data-ttu-id="0a924-172">Microsoft 365 [관리 센터에서](https://admin.microsoft.com/)청구를 **클릭한** 다음 서비스 **구매로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a924-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="0a924-173">선택 **Microsoft 365 E5** 무료 평가판 **시작 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a924-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![이미지 of_Microsoft 365 E5 무료 평가판 시작 페이지](../../media/mtp-eval-24.png)

3. <span data-ttu-id="0a924-175">확인 기본 설정 선택: 문자 메시지 또는 전화를 통해 선택</span><span class="sxs-lookup"><span data-stu-id="0a924-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="0a924-176">결정한 후 전화 번호를 입력하고 **선택에** 따라 문자 보내기 또는 전화 걸기 를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="0a924-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![이미지 of_Microsoft 365 E5 무료 평가판 시작 페이지에서 로봇이 아냐는 것을 증명하기 위해 코드를 보내기 위한 연락처 세부 정보를 요청합니다.](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="0a924-178">확인 코드를 입력하고 무료 **평가판 시작 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a924-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![이미지 of_Microsoft 365 E5 무료 평가판 시작 페이지에서 시스템이 로봇이 아 아니라는 것을 증명하기 위해 전송된 검증 코드를 입력할 수 있습니다.](../../media/mtp-eval-26.png)

5. <span data-ttu-id="0a924-180">지금 **사용해 보시고** 평가판을 Microsoft 365 E5 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![이미지 of_Microsoft 365 E5 무료 평가판 시작 페이지에서 지금 사용해기 단추를 시작해야 합니다.](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="0a924-182">관리 센터 **Microsoft 365 활성**  >  **사용자로**  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="0a924-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="0a924-183">사용자 계정을 선택하고 제품 라이선스 관리를 선택한 다음 라이선스를 Office 365 E5에서 **Microsoft 365 E5.**</span><span class="sxs-lookup"><span data-stu-id="0a924-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="0a924-184">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-184">Click **Save**.</span></span>

   ![of_Microsoft 라이선스를 선택할 수 있는 이미지 of_Microsoft 365 Microsoft 365 E5 페이지](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="0a924-186">전역 관리자 계정을 다시 선택한 다음 사용자 이름 **관리를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="0a924-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![계정 of_Microsoft 사용자 이름 관리를 선택할 수 있는 365 관리 센터 페이지 이미지](../../media/mtp-eval-29.png)

8. <span data-ttu-id="0a924-188">[선택 사항] 이전 단계에서  onmicrosoft.com 따라 도메인을 사용자 도메인으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="0a924-189">**변경 사항 저장** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-189">Click **Save changes**.</span></span>

   ![도메인 of_Microsoft 변경할 수 있는 365 관리 센터 페이지 이미지](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="0a924-191">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0a924-191">Next step</span></span>
|[<span data-ttu-id="0a924-192">3단계: 온보드 & 구성</span><span class="sxs-lookup"><span data-stu-id="0a924-192">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="0a924-193">각 Microsoft 365 Defender 평가판 Microsoft 365 랩 또는 파일럿 환경에 대해 각 Defender 기조를 구성하고 끝점을 온보딩합니다.</span><span class="sxs-lookup"><span data-stu-id="0a924-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
