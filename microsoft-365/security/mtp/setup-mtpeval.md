---
title: Microsoft 365 Defender 평가판 랩 또는 파일럿 환경 설정
description: Microsoft 365 보안 센터에 액세스 한 후 Microsoft 365 Defender 평가판 랩 환경 설정
keywords: Microsoft Threat Protection 평가판 설치, Microsoft Threat Protection 파일럿 설치, microsoft threat protection 체험, Microsoft Threat Protection 평가 실험 설치
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
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 503b7a6a6b3ad6394293e9f70dbdd336f6bee9dd
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131312"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="a6189-104">Microsoft 365 Defender 평가판 랩 환경 설정</span><span class="sxs-lookup"><span data-stu-id="a6189-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a6189-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="a6189-105">**Applies to:**</span></span>
- <span data-ttu-id="a6189-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6189-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="a6189-107">Microsoft 365 Defender 평가판 랩 또는 파일럿 환경을 만들고 배포 하는 과정은 다음 3 단계로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="a6189-108">[![1 단계: 준비](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="a6189-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="a6189-109">1 단계: 준비</span><span class="sxs-lookup"><span data-stu-id="a6189-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |![2 단계: 설정](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="a6189-111">2 단계: 설정</span><span class="sxs-lookup"><span data-stu-id="a6189-111">Phase 2: Set up</span></span> |<span data-ttu-id="a6189-112">[![3 단계: 온보드](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="a6189-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span></span><br/>[<span data-ttu-id="a6189-113">3 단계: 온보드</span><span class="sxs-lookup"><span data-stu-id="a6189-113">Phase 3: Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="a6189-114">[![파일럿으로 돌아가기](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="a6189-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="a6189-115">파일럿 playbook 돌아가기</span><span class="sxs-lookup"><span data-stu-id="a6189-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="a6189-116">*사용자가 여기 있어!*</span><span class="sxs-lookup"><span data-stu-id="a6189-116">*You are here!*</span></span>  | | |


<span data-ttu-id="a6189-117">현재 설정 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-117">You're currently in the set up phase.</span></span> <span data-ttu-id="a6189-118">초기 단계를 수행 하 여 Microsoft 365 보안 센터에 액세스 한 다음 평가판 랩 또는 파일럿 환경을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="a6189-119">Microsoft 365 E5 라이선스를 등록 하는 데 사용할 수 있는 *onmicrosoft.com* 테 넌 트를 생성 하기 위해 Office 365 또는 Azure Active Directory 구독에 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="a6189-120">기존 Office 365 또는 Azure Active Directory 구독이 이미 있는 경우에는 Office 365 E5 평가판 또는 파일럿 테 넌 트 만들기 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="a6189-121">이 단계에서는 다음을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="a6189-122">Office 365 E5 평가판 테 넌 트 만들기</span><span class="sxs-lookup"><span data-stu-id="a6189-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="a6189-123">Microsoft 365 평가판 구독 사용</span><span class="sxs-lookup"><span data-stu-id="a6189-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="a6189-124">Office 365 E5 평가판 테 넌 트 만들기</span><span class="sxs-lookup"><span data-stu-id="a6189-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="a6189-125">기존 Office 365 또는 Azure Active Directory 구독이 이미 있는 경우에는 Office 365 E5 평가판 테 넌 트 만들기 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="a6189-126">[Office 365 E5 제품 포털로](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) 이동 하 여 **무료 평가판** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![이미지 of_Office 365 E5 무료 평가판 페이지](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="a6189-128">전자 메일 주소 (개인 또는 회사)를 입력 하 여 평가판 등록을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="a6189-129">**계정 설정을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-129">Click **Set up account**.</span></span>

   ![이미지 of_Office 365 E5 평가판 등록 설정 페이지](../../media/mtp-eval-10.png)

3. <span data-ttu-id="a6189-131">성, 성, 근무처 전화 번호, 회사 이름, 회사 크기, 국가 또는 지역을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![이미지 of_Office 365 E5 평가판 등록 설정 페이지 이름, 전화 번호 및 회사 정보를 요청 합니다.](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="a6189-133">여기에서 설정 하는 국가 또는 지역에 따라 Office 365이 호스팅될 데이터 센터 지역이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="a6189-134">텍스트 메시지 또는 통화를 통해 확인 기본 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="a6189-135">**확인 코드 보내기를** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-135">Click **Send Verification Code**.</span></span> 

   ![이미지 of_Office 365 E5 평가판 등록 설정 페이지 확인 기본 설정 요청](../../media/mtp-eval-12.png)

5. <span data-ttu-id="a6189-137">테 넌 트에 대 한 사용자 지정 도메인 이름을 설정 하 고 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Image of_Office 365 E5 평가판 등록 설정 페이지에서 사용자 지정 도메인 이름을 설정할 수 있습니다.](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="a6189-139">테 넌 트의 전역 관리자가 되는 첫 번째 id를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="a6189-140">**이름** 및 **암호** 를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="a6189-141">**로그인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-141">Click **Sign up**.</span></span>

   ![이미지 of_Office 365 E5 평가판 등록 설정 페이지에서 비즈니스 id를 설정할 수 있습니다.](../../media/mtp-eval-14.png)

7. <span data-ttu-id="a6189-143">Office 365 E5 평가판 테 넌 트 프로 비전을 완료 하려면 **설치로 이동을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Office 365 E5 평가판 등록 설정 페이지에서 이동 설정 단추를 클릭 하 라는 메시지가 표시 되는 모양](../../media/mtp-eval-15.png)

8. <span data-ttu-id="a6189-145">회사 도메인을 Office 365 테 넌 트에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="a6189-146">반드시 **이미 소유한 도메인 연결** 을 선택 하 고 도메인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="a6189-147">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-147">Click **Next**.</span></span>

   ![사용자의 로그인 및 전자 메일을 개인 설정 해야 하는 이미지 of_Office 365 E5 설정 페이지](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="a6189-149">TXT 또는 MX 레코드를 추가 하 여 도메인 소유권을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="a6189-150">TXT 또는 MX 레코드를 도메인에 추가한 후에는 **확인** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![이미지 of_Office 365 E5 설치 페이지 도메인을 확인 하려면 MX 레코드의 TXT를 추가 해야 합니다.](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="a6189-152">반드시 테 넌 트에 대 한 사용자 계정을 더 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="a6189-153">**다음** 을 클릭 하 여이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-153">You can skip this step by clicking **Next**.</span></span>

    ![이미지 of_Office 365 E5 설치 페이지 더 많은 사용자를 추가할 수 있습니다.](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="a6189-155">반드시 Office 앱을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="a6189-156">이 단계를 건너뛰려면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-156">Click **Next** to skip this step.</span></span> 

    ![Office 앱을 설치할 수 있는 이미지 of_Office 365 E5 페이지](../../media/mtp-eval-19.png)

12. <span data-ttu-id="a6189-158">반드시 전자 메일 메시지를 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="a6189-159">이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-159">Again, you can skip this step.</span></span>

    ![이미지 of_Office 365 E5 전자 메일 메시지를 마이그레이션할지 여부를 설정할 수 있습니다.](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="a6189-161">온라인 서비스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-161">Choose online services.</span></span> <span data-ttu-id="a6189-162">**Exchange** 를 선택 하 고 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-162">Select **Exchange** and click **Next**.</span></span> 

    ![온라인 서비스를 선택할 수 있는 365 E5 이미지 of_Office](../../media/mtp-eval-21.png)

14. <span data-ttu-id="a6189-164">도메인에 MX, CNAME 및 TXT 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="a6189-165">완료 되 면 **확인** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-165">When completed, select **Verify**.</span></span>

    ![Image of_Office 365 E5 여기에서 DNS 레코드를 추가할 수 있습니다.](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="a6189-167">축 하 합니다, Office 365 테 넌 트의 프로 비전을 완료 했습니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![이미지 of_Office 365 E5 설치 완료 확인 페이지](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="a6189-169">Microsoft 365 평가판 구독 사용</span><span class="sxs-lookup"><span data-stu-id="a6189-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="a6189-170">평가판에 등록 하면 월별 사용자 라이선스 25 개를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="a6189-171">자세한 내용은 [M365 구독을 시도해 보거나 구매](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a6189-171">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="a6189-172">[Microsoft 365 관리 센터](https://admin.microsoft.com/)에서 **대금 청구** 를 클릭 하 고 **서비스 구매** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="a6189-173">**Microsoft 365 E5** 를 선택 하 고 **무료 평가판 시작** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Image of_Microsoft 365 E5 Start 무료 평가판 페이지](../../media/mtp-eval-24.png)

3. <span data-ttu-id="a6189-175">텍스트 메시지 또는 통화를 통해 확인 기본 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="a6189-176">전화 번호를 입력 하 고 **선택한 내용에** 따라 통화를 선택 하거나 **내게 전화** 를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![이미지 of_Microsoft 365 E5 시작 무료 평가판 페이지에서 로봇을 증명할 코드를 보내도록 연락처 정보를 요청 합니다.](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="a6189-178">확인 코드를 입력 하 고 **무료 평가판 시작** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![Image of_Microsoft 365 E5 Start 무료 평가판 페이지에서 사용자가 로봇이 아님을 입증 하기 위해 전송 되는 시스템의 확인 코드를 작성할 수 있습니다.](../../media/mtp-eval-26.png)

5. <span data-ttu-id="a6189-180">Microsoft 365 E5 평가판을 확인 하려면 **지금 시도** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Image of_Microsoft 365 E5 Start 무료 평가판 페이지를 시작 하려면 지금 사용해 보기 단추를 클릭 합니다.](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="a6189-182">**Microsoft 365 관리 센터**  >  **사용자**  >  **활성 사용자** 로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="a6189-183">사용자 계정을 선택 하 고 **제품 라이선스 관리** 를 선택한 다음 Office 365 E5에서 **Microsoft 365 e5** 로 라이선스를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="a6189-184">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-184">Click **Save**.</span></span>

   ![Image of_Microsoft 365 관리 센터 페이지 Microsoft 365 E5 라이선스를 선택할 수 있습니다.](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="a6189-186">전역 관리자 계정을 다시 선택 하 고 **사용자 이름 관리** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![이미지 of_Microsoft 365 관리 센터 페이지 계정을 선택 하 고 사용자 이름을 관리할 수 있습니다.](../../media/mtp-eval-29.png)

8. <span data-ttu-id="a6189-188">반드시 이전 단계에서 선택한 사항에 따라 도메인을 *onmicrosoft.com* 에서 자체 도메인으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="a6189-189">**변경 내용 저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-189">Click **Save changes**.</span></span>

   ![이미지 of_Microsoft 365 관리 센터 페이지 도메인 기본 설정을 변경할 수 있음](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="a6189-191">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a6189-191">Next step</span></span>
|[<span data-ttu-id="a6189-192">3 단계: 온보드 & 구성</span><span class="sxs-lookup"><span data-stu-id="a6189-192">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="a6189-193">Microsoft 365 Defender 평가판 lab 또는 파일럿 환경에 대해 각 Microsoft 365 Defender를 구성 하 고 끝점을 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6189-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
