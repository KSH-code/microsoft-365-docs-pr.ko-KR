---
title: Microsoft Threat Protection 평가판 랩 환경 설정
description: Microsoft 365 보안 센터에 액세스 한 후 Microsoft Threat Protection 평가판 랩 환경 설정
keywords: Microsoft Threat Protection 평가판 설치, microsoft threat protection, Microsoft Threat Protection 평가 실험 설정 시도
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
ms.openlocfilehash: 50557b0824999f0220af4d12b906b0274db4471e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049618"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="32bc5-104">Microsoft Threat Protection 평가판 랩 환경 설정</span><span class="sxs-lookup"><span data-stu-id="32bc5-104">Set up your Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="32bc5-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="32bc5-105">**Applies to:**</span></span>
- <span data-ttu-id="32bc5-106">Microsoft 위협 방지</span><span class="sxs-lookup"><span data-stu-id="32bc5-106">Microsoft Threat Protection</span></span> 


<span data-ttu-id="32bc5-107">Microsoft Threat Protection 평가판 랩 환경을 만들고 배포 하는 과정은 다음 세 단계로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Microsoft Threat Protection 평가 랩 준비" />
      <br/><span data-ttu-id="32bc5-109">1 단계: 준비</a></span><span class="sxs-lookup"><span data-stu-id="32bc5-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Microsoft Threat Protection 평가 랩 설정" />
      <br/><span data-ttu-id="32bc5-111">2 단계: 설치</a></span><span class="sxs-lookup"><span data-stu-id="32bc5-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
Microsoft Threat Protection 평가판 테스트 환경에 대 한 각 Microsoft Threat Protection을 구성 하 고 끝점을 온보드" />
      <br/><span data-ttu-id="32bc5-113">3 단계: 온보드 & 구성</a></span><span class="sxs-lookup"><span data-stu-id="32bc5-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="32bc5-114">현재 설정 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-114">You are currently in the set up phase.</span></span> <span data-ttu-id="32bc5-115">초기 단계를 수행 하 여 Microsoft 365 보안 센터에 액세스 한 다음 평가판 랩 환경을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-115">Take the initial steps to access Microsoft 365 Security Center then setup your trial lab environment.</span></span>

<span data-ttu-id="32bc5-116">Microsoft 365 E5 라이선스를 등록 하는 데 사용할 수 있는 *onmicrosoft.com* 테 넌 트를 생성 하기 위해 Office 365 또는 Azure Active Directory 구독에 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-116">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="32bc5-117">기존 Office 365 또는 Azure Active Directory 구독이 이미 있는 경우에는 Office 365 E5 평가판 테 넌 트 만들기 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-117">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

<span data-ttu-id="32bc5-118">이 단계에서는 다음을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-118">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="32bc5-119">Office 365 E5 평가판 테 넌 트 만들기</span><span class="sxs-lookup"><span data-stu-id="32bc5-119">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="32bc5-120">Microsoft 365 평가판 구독 사용</span><span class="sxs-lookup"><span data-stu-id="32bc5-120">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="32bc5-121">Office 365 E5 평가판 테 넌 트 만들기</span><span class="sxs-lookup"><span data-stu-id="32bc5-121">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="32bc5-122">기존 Office 365 또는 Azure Active Directory 구독이 이미 있는 경우에는 Office 365 E5 평가판 테 넌 트 만들기 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-122">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="32bc5-123">[Office 365 E5 제품 포털로](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) 이동 하 여 **무료 평가판**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-123">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>
<span data-ttu-id="32bc5-124">![이미지 of_page](../../media/mtp-eval-9.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-124">![Image of_page](../../media/mtp-eval-9.png)</span></span> <br>
  
2. <span data-ttu-id="32bc5-125">전자 메일 주소 (개인 또는 회사)를 입력 하 여 평가판 등록을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-125">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="32bc5-126">**계정 설정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-126">Click **Set up account**.</span></span>
<span data-ttu-id="32bc5-127">![이미지 of_page](../../media/mtp-eval-10.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-127">![Image of_page](../../media/mtp-eval-10.png)</span></span> <br> 

3. <span data-ttu-id="32bc5-128">성, 성, 근무처 전화 번호, 회사 이름, 회사 크기, 국가 또는 지역을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-128">Fill in your first name, last name, business phone number, company name, company size and country or region.</span></span>  
<br>![이미지 of_page](../../media/mtp-eval-11.png) <br>
>[!NOTE]
><span data-ttu-id="32bc5-130">여기에서 설정 하는 국가 또는 지역에 따라 Office 365이 호스팅될 데이터 센터 지역이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-130">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="32bc5-131">텍스트 메시지 또는 통화를 통해 확인 기본 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-131">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="32bc5-132">**확인 코드 보내기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-132">Click **Send Verification Code**.</span></span> 
<span data-ttu-id="32bc5-133">![이미지 of_page](../../media/mtp-eval-12.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-133">![Image of_page](../../media/mtp-eval-12.png)</span></span> <br>

5. <span data-ttu-id="32bc5-134">테 넌 트에 대 한 사용자 지정 도메인 이름을 설정 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-134">Set the custom domain name for your tenant, then click **Next**.</span></span>
<br><span data-ttu-id="32bc5-135">![이미지 of_page](../../media/mtp-eval-13.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-135">![Image of_page](../../media/mtp-eval-13.png)</span></span> <br>
 
6. <span data-ttu-id="32bc5-136">테 넌 트에 대 한 전역 관리자가 될 첫 번째 id를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-136">Set up the first identity which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="32bc5-137">**이름** 및 **암호**를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-137">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="32bc5-138">**로그인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-138">Click **Sign up**.</span></span>
<span data-ttu-id="32bc5-139">![이미지 of_page](../../media/mtp-eval-14.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-139">![Image of_page](../../media/mtp-eval-14.png)</span></span> <br>
<span data-ttu-id="32bc5-140">&</span><span class="sxs-lookup"><span data-stu-id="32bc5-140">c</span></span>
7. <span data-ttu-id="32bc5-141">Office 365 E5 평가판 테 넌 트 프로 비전을 완료 하려면 **설치로 이동을** 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-141">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>
<br><span data-ttu-id="32bc5-142">![이미지 of_page](../../media/mtp-eval-15.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-142">![Image of_page](../../media/mtp-eval-15.png)</span></span> <br>

8. <span data-ttu-id="32bc5-143">회사 도메인을 Office 365 테 넌 트에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-143">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="32bc5-144">반드시 **이미 소유한 도메인 연결** 을 선택 하 고 도메인 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-144">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="32bc5-145">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-145">Click **Next**.</span></span>
<br><span data-ttu-id="32bc5-146">![이미지 of_page](../../media/mtp-eval-16.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-146">![Image of_page](../../media/mtp-eval-16.png)</span></span> <br>
 
9. <span data-ttu-id="32bc5-147">도메인 소유권을 확인 하려면 TXT 또는 MX 레코드를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-147">You will need to add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="32bc5-148">TXT 또는 MX 레코드를 도메인에 추가한 후에는 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-148">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>
<br><span data-ttu-id="32bc5-149">![이미지 of_page](../../media/mtp-eval-17.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-149">![Image of_page](../../media/mtp-eval-17.png)</span></span> <br>
 
10. <span data-ttu-id="32bc5-150">반드시 테 넌 트에 대 한 사용자 계정을 더 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-150">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="32bc5-151">**다음**을 클릭 하 여이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-151">You can skip this step by clicking **Next**.</span></span>
<span data-ttu-id="32bc5-152">![이미지 of_page](../../media/mtp-eval-18.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-152">![Image of_page](../../media/mtp-eval-18.png)</span></span> <br>
 
11. <span data-ttu-id="32bc5-153">반드시 Office 앱을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-153">[Optional] Download Office apps.</span></span> <span data-ttu-id="32bc5-154">이 단계를 건너뛰려면 **다음** 을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-154">Click **Next** to skip this step.</span></span> 
<br><span data-ttu-id="32bc5-155">![이미지 of_page](../../media/mtp-eval-19.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-155">![Image of_page](../../media/mtp-eval-19.png)</span></span> <br>

12. <span data-ttu-id="32bc5-156">반드시 전자 메일 메시지를 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-156">[Optional] Migrate email messages.</span></span> <span data-ttu-id="32bc5-157">이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-157">Again, you can skip this step.</span></span>
<br><span data-ttu-id="32bc5-158">![이미지 of_page](../../media/mtp-eval-20.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-158">![Image of_page](../../media/mtp-eval-20.png)</span></span> <br>
 
13. <span data-ttu-id="32bc5-159">온라인 서비스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-159">Choose online services.</span></span> <span data-ttu-id="32bc5-160">**Exchange** 를 선택 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-160">Select **Exchange** and click **Next**.</span></span> 
<br><span data-ttu-id="32bc5-161">![이미지 of_page](../../media/mtp-eval-21.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-161">![Image of_page](../../media/mtp-eval-21.png)</span></span> <br>

14. <span data-ttu-id="32bc5-162">도메인에 MX, CNAME 및 TXT 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-162">Add MX, CNAME and TXT records to your domain.</span></span> <span data-ttu-id="32bc5-163">완료 되 면 **확인**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-163">When completed, select **Verify**.</span></span>
<br><span data-ttu-id="32bc5-164">![이미지 of_page](../../media/mtp-eval-22.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-164">![Image of_page](../../media/mtp-eval-22.png)</span></span> <br>
 
15. <span data-ttu-id="32bc5-165">축 하 합니다, Office 365 테 넌 트의 프로 비전을 완료 했습니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-165">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>
<br><span data-ttu-id="32bc5-166">![이미지 of_page](../../media/mtp-eval-23.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-166">![Image of_page](../../media/mtp-eval-23.png)</span></span> <br>

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="32bc5-167">Microsoft 365 평가판 구독 사용</span><span class="sxs-lookup"><span data-stu-id="32bc5-167">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="32bc5-168">평가판에 등록 하면 월별 사용자 라이선스 25 개를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-168">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="32bc5-169">자세한 내용은 [M365 구독을 시도해 보거나 구매](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="32bc5-169">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="32bc5-170">[Microsoft 365 관리 센터](https://admin.microsoft.com/)에서 **대금 청구** 를 클릭 하 고 **서비스 구매**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-170">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="32bc5-171">**Microsoft 365 E5** 를 선택 하 고 **무료 평가판 시작**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-171">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 
<span data-ttu-id="32bc5-172">![이미지 of_page](../../media/mtp-eval-24.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-172">![Image of_page](../../media/mtp-eval-24.png)</span></span> <br>

3. <span data-ttu-id="32bc5-173">텍스트 메시지 또는 통화를 통해 확인 기본 설정을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-173">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="32bc5-174">전화 번호를 입력 하 고 **선택한 내용에** 따라 통화를 선택 하거나 **내게 전화** 를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-174">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>
<span data-ttu-id="32bc5-175">![이미지 of_page](../../media/mtp-eval-25.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-175">![Image of_page](../../media/mtp-eval-25.png)</span></span> <br>
 
4. <span data-ttu-id="32bc5-176">확인 코드를 입력 하 고 **무료 평가판 시작**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-176">Enter the verification code and click **Start your free trial**.</span></span> 
<br><span data-ttu-id="32bc5-177">![이미지 of_page](../../media/mtp-eval-26.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-177">![Image of_page](../../media/mtp-eval-26.png)</span></span> <br>

5. <span data-ttu-id="32bc5-178">Microsoft 365 E5 평가판을 확인 하려면 **지금 시도** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-178">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>
<br><span data-ttu-id="32bc5-179">![이미지 of_page](../../media/mtp-eval-27.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-179">![Image of_page](../../media/mtp-eval-27.png)</span></span> <br>
 
6. <span data-ttu-id="32bc5-180">**Microsoft 365 관리 센터** > **사용자** > **활성 사용자**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-180">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="32bc5-181">사용자 계정을 선택 하 고 **제품 라이선스 관리**를 선택한 다음 Office 365 E5에서 **Microsoft 365 e5**로 라이선스를 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-181">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="32bc5-182">**저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-182">Click **Save**.</span></span>
<span data-ttu-id="32bc5-183">![이미지 of_page](../../media/mtp-eval-28.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-183">![Image of_page](../../media/mtp-eval-28.png)</span></span> <br>
 
7. <span data-ttu-id="32bc5-184">전역 관리자 계정을 다시 선택 하 고 **사용자 이름 관리**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-184">Select the global administrator account again then click **Manage username**.</span></span>
<br><span data-ttu-id="32bc5-185">![이미지 of_page](../../media/mtp-eval-29.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-185">![Image of_page](../../media/mtp-eval-29.png)</span></span> <br>

8. <span data-ttu-id="32bc5-186">반드시 이전 단계에서 선택한 사항에 따라 도메인을 *onmicrosoft.com* 에서 자체 도메인으로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-186">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="32bc5-187">**변경 내용 저장**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-187">Click **Save changes**.</span></span>
<br><span data-ttu-id="32bc5-188">![이미지 of_page](../../media/mtp-eval-30.png)</span><span class="sxs-lookup"><span data-stu-id="32bc5-188">![Image of_page](../../media/mtp-eval-30.png)</span></span> <br>



## <a name="next-step"></a><span data-ttu-id="32bc5-189">다음 단계</span><span class="sxs-lookup"><span data-stu-id="32bc5-189">Next step</span></span>
<span data-ttu-id="32bc5-190">||| |:-------|:-----| config-onboard)</span><span class="sxs-lookup"><span data-stu-id="32bc5-190">||| |:-------|:-----|config-onboard.png)</span></span> <br><span data-ttu-id="32bc5-191">[3 단계: & 구성 (온보드](config-mtpeval.md) |) Microsoft Threat Protection 평가판 테스트 환경에 대 한 각 Microsoft Threat Protection을 구성 하 고 끝점을 온보드 합니다.</span><span class="sxs-lookup"><span data-stu-id="32bc5-191">[Phase 3: Configure & Onboard](config-mtpeval.md) | Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints.</span></span>
