---
title: 평가판 Microsoft 365 Defender 파일럿 환경 설정
description: Access Microsoft 365 보안 센터에 액세스한 다음 Microsoft 365 Defender 테스트 랩 환경 설정
keywords: Microsoft 365 Defender 설치, 파일럿 Microsoft 365 Defender 테스트, Microsoft 365 Defender 테스트 Microsoft 365 Defender 테스트
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6db3003aa6465df90a3d2e4af55b28ccccf44100
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454736"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a><span data-ttu-id="03115-104">랩 환경에서 Microsoft 365 Defender 평가판 설정</span><span class="sxs-lookup"><span data-stu-id="03115-104">Set up your Microsoft 365 Defender trial in a lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="03115-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="03115-105">**Applies to:**</span></span>
- <span data-ttu-id="03115-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03115-106">Microsoft 365 Defender</span></span> 

<span data-ttu-id="03115-107">이 항목에서는 전용 랩 환경을 설정하는 데 대해 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="03115-107">This topic guides you to set up a dedicated lab environment.</span></span> <span data-ttu-id="03115-108">프로덕션 환경의 평가판 설정에 대한 [](eval-overview.md) 자세한 내용은 새로운 평가 및 파일럿 테스트 Microsoft 365 Defender 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03115-108">For information on setting up a trial in production, see the new [Evaluate and pilot Microsoft 365 Defender](eval-overview.md) guide.</span></span> 

## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="03115-109">평가판 Office 365 E5 테넌트 만들기</span><span class="sxs-lookup"><span data-stu-id="03115-109">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="03115-110">기존 Office 365 또는 Azure Active Directory 있는 경우 평가판 테넌트 만들기 Office 365 E5 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03115-110">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="03115-111">제품 [포털로 Office 365 E5 무료](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) **평가판 을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03115-111">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![이미지 of_Office 365 E5 무료 평가판 페이지](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="03115-113">전자 메일 주소(개인 또는 회사)를 입력하여 평가판 등록을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="03115-113">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="03115-114">계정 **설정 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="03115-114">Click **Set up account**.</span></span>

   ![이미지 of_Office 365 E5 평가판 등록 설정 페이지](../../media/mtp-eval-10.png)

3. <span data-ttu-id="03115-116">이름, 성, 회사 전화 번호, 회사 이름, 회사 크기, 국가 또는 지역을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03115-116">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![이름of_Office 전화 및 회사 세부 정보를 요청하는 365 E5 평가판 등록 설정 페이지 이미지](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="03115-118">여기서 설정한 국가 또는 지역은 호스트할 데이터 센터 Office 365 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="03115-118">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="03115-119">확인 기본 설정 선택: 문자 메시지 또는 전화를 통해 선택</span><span class="sxs-lookup"><span data-stu-id="03115-119">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="03115-120">확인 **코드 보내기 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="03115-120">Click **Send Verification Code**.</span></span> 

   ![확인 of_Office 묻는 365 E5 평가판 등록 설정 페이지 이미지](../../media/mtp-eval-12.png)

5. <span data-ttu-id="03115-122">테넌트에 대한 사용자 지정 도메인 이름을 설정하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="03115-122">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![사용자 of_Office 설정할 수 있는 365 E5 평가판 등록 설정 페이지 이미지](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="03115-124">테넌트의 전역 관리자가 될 첫 번째 ID를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="03115-124">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="03115-125">이름 및 **암호를** **입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="03115-125">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="03115-126">**등록** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03115-126">Click **Sign up**.</span></span>

   ![비즈니스 of_Office 설정할 수 있는 365 E5 평가판 등록 설정 페이지 이미지](../../media/mtp-eval-14.png)

7. <span data-ttu-id="03115-128">설치로 **이동을 클릭하여** Office 365 E5 테넌트 프로비전을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="03115-128">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![설치 Office 365 E5 클릭하라는 메시지를 표시하는 평가판 등록 설정 페이지의 이미지](../../media/mtp-eval-15.png)

8. <span data-ttu-id="03115-130">커넥트 도메인을 Office 365 테넌트에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="03115-130">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="03115-131">[선택 사항] 이미 **커넥트** 도메인을 선택하고 도메인 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="03115-131">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="03115-132">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03115-132">Click **Next**.</span></span>

   ![로그인 of_Office 전자 메일을 개인 설정해야 하는 365 E5 설치 페이지 이미지](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="03115-134">TXT 또는 MX 레코드를 추가하여 도메인 소유권의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="03115-134">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="03115-135">도메인에 TXT 또는 MX 레코드를 추가한 후 확인 을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03115-135">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![도메인을 of_Office MX 레코드의 TXT를 추가해야 하는 365 E5 설치 페이지 이미지](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="03115-137">[선택 사항] 테넌트에 대한 사용자 계정을 더 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03115-137">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="03115-138">다음 을 클릭하여 이 단계를 건너뛸 **수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="03115-138">You can skip this step by clicking **Next**.</span></span>

    ![더 of_Office 추가할 수 있는 365 E5 설치 페이지 이미지](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="03115-140">[선택 사항] 앱 Office 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="03115-140">[Optional] Download Office apps.</span></span> <span data-ttu-id="03115-141">이 **단계를** 건너뛰려면 다음을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03115-141">Click **Next** to skip this step.</span></span> 

    ![of_Office 앱을 설치할 수 있는 365 E5 Office 이미지](../../media/mtp-eval-19.png)

12. <span data-ttu-id="03115-143">[선택 사항] 전자 메일 메시지를 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="03115-143">[Optional] Migrate email messages.</span></span> <span data-ttu-id="03115-144">이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03115-144">Again, you can skip this step.</span></span>

    ![전자 of_Office 마이그레이션할지 여부를 설정할 수 있는 365 E5 이미지](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="03115-146">온라인 서비스를 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="03115-146">Choose online services.</span></span> <span data-ttu-id="03115-147">다음 **Exchange** 선택하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="03115-147">Select **Exchange** and click **Next**.</span></span> 

    ![온라인 of_Office 선택할 수 있는 365 E5 이미지](../../media/mtp-eval-21.png)

14. <span data-ttu-id="03115-149">도메인에 MX, CNAME 및 TXT 레코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="03115-149">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="03115-150">완료되면 확인 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="03115-150">When completed, select **Verify**.</span></span>

    ![여기에서 of_Office 365 E5를 사용하여 DNS 레코드를 추가할 수 있습니다.](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="03115-152">축하합니다. 사용자 테넌트의 프로비전을 Office 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03115-152">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![이미지 of_Office 365 E5 설치 완료 확인 페이지](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="03115-154">평가판 Microsoft 365 사용</span><span class="sxs-lookup"><span data-stu-id="03115-154">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="03115-155">평가판에 등록하면 한 달 동안 사용할 25개 사용자 라이선스가 부여됩니다.</span><span class="sxs-lookup"><span data-stu-id="03115-155">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="03115-156">자세한 [내용은 M365](../../commerce/try-or-buy-microsoft-365.md) 구독 시도 또는 구입을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03115-156">See [Try or Buy an M365 subscription](../../commerce/try-or-buy-microsoft-365.md) for details.</span></span>

1. <span data-ttu-id="03115-157">Microsoft 365 관리 [센터에서](https://admin.microsoft.com/)청구를 **클릭한** 다음 서비스 **구매로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="03115-157">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="03115-158">선택 **Microsoft 365 E5** 무료 평가판 **시작 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="03115-158">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![이미지 of_Microsoft 365 E5 무료 평가판 시작 페이지](../../media/mtp-eval-24.png)

3. <span data-ttu-id="03115-160">확인 기본 설정 선택: 문자 메시지 또는 전화를 통해 선택</span><span class="sxs-lookup"><span data-stu-id="03115-160">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="03115-161">결정한 후 전화 번호를 입력하고 **선택에** 따라 문자 보내기 또는 전화 걸기 를 선택합니다. </span><span class="sxs-lookup"><span data-stu-id="03115-161">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![이미지 of_Microsoft 365 E5 무료 평가판 시작 페이지에서 로봇이 아냐는 것을 증명하기 위해 코드를 보내기 위한 연락처 세부 정보를 요청합니다.](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="03115-163">확인 코드를 입력하고 무료 **평가판 시작 을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="03115-163">Enter the verification code and click **Start your free trial**.</span></span>

   ![이미지 of_Microsoft 365 E5 무료 평가판 시작 페이지에서 시스템이 로봇이 아 아니라는 것을 증명하기 위해 전송된 검증 코드를 입력할 수 있습니다.](../../media/mtp-eval-26.png)

5. <span data-ttu-id="03115-165">지금 **사용해 보시고** 평가판을 Microsoft 365 E5 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03115-165">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![이미지 of_Microsoft 365 E5 무료 평가판 시작 페이지에서 지금 사용해기 단추를 시작해야 합니다.](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="03115-167">사용자 센터 **Microsoft 365 관리 활성**  >    >  **사용자로 이동 합니다.**</span><span class="sxs-lookup"><span data-stu-id="03115-167">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="03115-168">사용자 계정을 선택하고 제품 라이선스 관리를 선택한 다음 라이선스를 사용자 계정에서 Office 365 E5 **Microsoft 365 E5.**</span><span class="sxs-lookup"><span data-stu-id="03115-168">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="03115-169">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03115-169">Click **Save**.</span></span>

   ![of_Microsoft 라이선스를 선택할 수 있는 이미지 of_Microsoft 365 Microsoft 365 E5 페이지](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="03115-171">전역 관리자 계정을 다시 선택한 다음 사용자 이름 **관리를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="03115-171">Select the global administrator account again then click **Manage username**.</span></span>

   ![계정 of_Microsoft 사용자 이름 관리를 선택할 수 있는 365 관리 센터 페이지 이미지](../../media/mtp-eval-29.png)

8. <span data-ttu-id="03115-173">[선택 사항] 이전 단계에서  onmicrosoft.com 따라 도메인을 사용자 도메인으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="03115-173">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="03115-174">**변경 사항 저장** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03115-174">Click **Save changes**.</span></span>

   ![도메인 of_Microsoft 변경할 수 있는 365 관리 센터 페이지 이미지](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="03115-176">다음 단계</span><span class="sxs-lookup"><span data-stu-id="03115-176">Next step</span></span>
|[<span data-ttu-id="03115-177">3단계: 온보드 & 구성</span><span class="sxs-lookup"><span data-stu-id="03115-177">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="03115-178">Microsoft 365 Defender 랩 또는 파일럿 환경에 대한 각 Microsoft 365 Defender 구성하고 끝점을 온보드합니다.</span><span class="sxs-lookup"><span data-stu-id="03115-178">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
