---
title: 그룹 및 사용자 구성하기 - 정치적 캠페인 개발/테스트 환경
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 0e22bcf3-bad3-42a4-b44f-276e0cf4790f
description: '요약: 정치적 캠페인 개발/테스트 환경의 사용자 및 그룹을 사용하여 Office 365 및 EMS(Enterprise Mobility + Security) 평가판 구독을 만듭니다.'
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 54d2543313c1a031974876d7fd09b453cc2ec24d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906543"
---
# <a name="configure-groups-and-users-for-a-political-campaign-devtest-environment"></a><span data-ttu-id="4e681-103">정치적 캠페인 개발/테스트 환경에 대해 그룹 및 사용자 구성</span><span class="sxs-lookup"><span data-stu-id="4e681-103">Configure groups and users for a political campaign dev/test environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4e681-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="4e681-104">**Applies to**</span></span>
- [<span data-ttu-id="4e681-105">Office 365용 Microsoft Defender 플랜 2</span><span class="sxs-lookup"><span data-stu-id="4e681-105">Microsoft Defender for Office 365 plan 2</span></span>](office-365-atp.md)

 <span data-ttu-id="4e681-106">**요약:** 정치적 캠페인 개발/테스트 환경의 사용자 및 그룹을 사용하여 Office 365 및 EMS(Enterprise Mobility + Security) 평가판 구독을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-106">**Summary:** Create Office 365 and Enterprise Mobility + Security (EMS) trial subscriptions with users and groups for a political campaign dev/test environment.</span></span>

<span data-ttu-id="4e681-107">이 문서의 절차에 따라 [정치적 캠페인, 비영리 조직 및 기타 기밀 조직에 대한 Microsoft 보안 지침](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) 솔루션을 위한 간소화된 사용자 계정 및 그룹을 포함하는 개발/테스트 환경을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-107">Use the instructions in this article to create a dev/test environment that includes simplified user accounts and groups for the [Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) solution.</span></span>

## <a name="phase-1-create-your-office-365-devtest-environment"></a><span data-ttu-id="4e681-108">1단계: Office 365 개발/테스트 환경 만들기</span><span class="sxs-lookup"><span data-stu-id="4e681-108">Phase 1: Create your Office 365 dev/test environment</span></span>

<span data-ttu-id="4e681-109">이 단계에서는 정치적 캠페인을 표방하는 가상의 조직을 위해 Office 365 E5 및 EMS(Enterprise Mobility + Security) E5에 대한 평가판 구독을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-109">In this phase, you obtain trial subscriptions for Office 365 E5 and Enterprise Mobility + Security (EMS) E5 for a fictional organization that represents a political campaign.</span></span>

<span data-ttu-id="4e681-110">먼저 [간단한 기본 구성](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)의 **2단계** 에 나와 있는 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="4e681-110">First, follow the instructions in **Phase 2** of [The lightweight base configuration](../../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>

<span data-ttu-id="4e681-111">다음으로, EMS E5 평가판 구독을 등록하고 평가판 구독과 동일한 조직에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-111">Next, sign up for the EMS E5 trial subscription and add it to the same organization as your trial subscription.</span></span>

1. <span data-ttu-id="4e681-112">필요한 경우 평가판 구독의 전역 관리자 계정 자격 증명으로 관리 센터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-112">If needed, sign in to the admin center with the credentials of the global administrator account of your trial subscription.</span></span> <span data-ttu-id="4e681-113">도움을 받으려면 [로그인하는 위치](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4e681-113">For help, see [Where to sign in](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="4e681-114">**관리** 타일을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-114">Click the **Admin** tile.</span></span>

3. <span data-ttu-id="4e681-115">브라우저의 **Microsoft 365 관리 센터** 탭에 있는 왼쪽 탐색 영역에서 **대금 청구 > 서비스 구매** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-115">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Billing > Purchase services**.</span></span>

4. <span data-ttu-id="4e681-p102">
            \*\*구매 서비스\*\* 페이지에서 \*\*Enterprise Mobility + Security E5\*\* 항목을 찾습니다. 마우스 포인터를 가져간 후 \*\*평가판 시작** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-p102">On the **Purchase services** page, find the **Enterprise Mobility + Security E5** item. Hover your mouse pointer over it and click **Start free trial**.</span></span>

5. <span data-ttu-id="4e681-118">**주문 확인** 페이지에서 **지금 평가판 사용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-118">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="4e681-119">**주문 접수** 페이지에서 **계속** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-119">On the **Order receipt** page, click **Continue**.</span></span>

<span data-ttu-id="4e681-120">그런 다음 전역 관리자 계정에 대해 EMS E5 라이선스를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-120">Next, enable the EMS E5 license for your global administrator account.</span></span>

1. <span data-ttu-id="4e681-121">브라우저의 **Microsoft 365 관리 센터** 탭에 있는 왼쪽 탐색 영역에서 **사용자 > 활성 사용자** 를 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-121">On the **Microsoft 365 admin center** tab in your browser, in the left navigation, click **Users > Active users**.</span></span>

2. <span data-ttu-id="4e681-122">전역 관리자 계정을 클릭한 다음, **제품 라이선스** 에 대해 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-122">Click your global administrator account, and then click **Edit** for **Product licenses**.</span></span>

3. <span data-ttu-id="4e681-123">**제품 라이선스** 창에서 **Enterprise Mobility + Security E5** 에 대한 제품 라이선스를 **설정** 으로 바꾸고 **저장** 을 클릭한 후 **닫기** 를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-123">On the **Product licenses** pane, turn the product license for **Enterprise Mobility + Security E5** to **On**, click **Save,** and then click **Close** twice.</span></span>

## <a name="phase-2-create-and-configure-your-azure-active-directory-ad-groups"></a><span data-ttu-id="4e681-124">2단계: Azure AD(Active Directory) 그룹 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="4e681-124">Phase 2: Create and configure your Azure Active Directory (AD) groups</span></span>

<span data-ttu-id="4e681-125">이 단계에서는 캡페인에 대한 Azure AD 그룹을 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-125">In this phase, you create and configure the Azure AD groups for your campaign.</span></span>

<span data-ttu-id="4e681-126">먼저 Azure Portal을 사용하여 일반적인 정치적 캠페인에 대한 그룹 집합을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-126">First, create a set of groups for a typical political campaign with the Azure portal.</span></span>

1. <span data-ttu-id="4e681-127">브라우저의 별도 탭에서 <https://portal.azure.com>의 Azure Portal로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-127">On a separate tab in your browser, go to the Azure portal at <https://portal.azure.com>.</span></span> <span data-ttu-id="4e681-128">필요한 경우 Office 365 E5 평가판 구독에 대한 전역 관리자 계정의 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-128">If needed, sign in with the credentials of the global administrator account for your Office 365 E5 trial subscription.</span></span>

2. <span data-ttu-id="4e681-129">Azure Portal에서 **Azure Active Directory > 사용자 및 그룹 > 모든 그룹** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-129">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>

3. <span data-ttu-id="4e681-130">이 목록의 각 그룹 이름에 대해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-130">Do the following steps for each group name in this list:</span></span>

   - <span data-ttu-id="4e681-131">Senior and strategic staff</span><span class="sxs-lookup"><span data-stu-id="4e681-131">Senior and strategic staff</span></span>

   - <span data-ttu-id="4e681-132">IT staff</span><span class="sxs-lookup"><span data-stu-id="4e681-132">IT staff</span></span>

   - <span data-ttu-id="4e681-133">Analytics staff</span><span class="sxs-lookup"><span data-stu-id="4e681-133">Analytics staff</span></span>

   - <span data-ttu-id="4e681-134">Regular core staff</span><span class="sxs-lookup"><span data-stu-id="4e681-134">Regular core staff</span></span>

   - <span data-ttu-id="4e681-135">Operations staff</span><span class="sxs-lookup"><span data-stu-id="4e681-135">Operations staff</span></span>

   - <span data-ttu-id="4e681-136">Field staff</span><span class="sxs-lookup"><span data-stu-id="4e681-136">Field staff</span></span>

1. <span data-ttu-id="4e681-137">**모든 그룹** 블레이드에서 **+ 새 그룹** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-137">On the **All groups** blade, click **+ New group**.</span></span>

2. <span data-ttu-id="4e681-138">**이름** 에 목록의 그룹 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-138">Type the group name from the list in **Name**.</span></span>

3. <span data-ttu-id="4e681-139">**멤버 자격** 에서 **동적 사용자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-139">Select **Dynamic user** in **Membership**.</span></span>

4. <span data-ttu-id="4e681-140">**Office 기능 사용** 에 **예** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-140">Click **Yes** for **Enable Office features**.</span></span>

5. <span data-ttu-id="4e681-141">**동적 쿼리 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-141">Click **Add dynamic query**.</span></span>

6. <span data-ttu-id="4e681-142">**사용자를 추가할 위치** 에서 **부서** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-142">In **Add users where**, select **department**.</span></span>

7. <span data-ttu-id="4e681-143">다음 필드에서 **같음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-143">In the next field, select **Equals**.</span></span>

8. <span data-ttu-id="4e681-144">다음 필드에 목록의 그룹 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-144">In the next field, type the group name from the list.</span></span>

9. <span data-ttu-id="4e681-145">**쿼리 추가** 를 클릭한 다음, **만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-145">Click **Add query**, and then click **Create**.</span></span>

10. <span data-ttu-id="4e681-146">**사용자 및 그룹 - 모든 그룹** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-146">Click **Users and groups - All groups**.</span></span>

<span data-ttu-id="4e681-147">다음으로, 멤버에 Office 365 E5 및 EMS E5 라이선스가 자동으로 할당되도록 그룹을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-147">Next, you configure the groups so that members are automatically assigned Office 365 E5 and EMS E5 licenses.</span></span>

1. <span data-ttu-id="4e681-148">Azure Portal에서 **Azure Active Directory > 라이선스 > 모든 제품** 을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-148">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>

2. <span data-ttu-id="4e681-149">목록에서 **Enterprise Mobility + Security E5** 및 **Office 365 Enterprise E5** 를 선택하고 **+ 할당** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-149">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **+ Assign**.</span></span>

3. <span data-ttu-id="4e681-150">**라이선스 할당** 블레이드에서 **사용자 및 그룹** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-150">In the **Assign license** blade, click **Users and groups**.</span></span>

4. <span data-ttu-id="4e681-151">그룹 목록에서 다음을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-151">In the list of groups, select the following:</span></span>

   - <span data-ttu-id="4e681-152">Analytics staff</span><span class="sxs-lookup"><span data-stu-id="4e681-152">Analytics staff</span></span>

   - <span data-ttu-id="4e681-153">Field staff</span><span class="sxs-lookup"><span data-stu-id="4e681-153">Field staff</span></span>

   - <span data-ttu-id="4e681-154">IT staff</span><span class="sxs-lookup"><span data-stu-id="4e681-154">IT staff</span></span>

   - <span data-ttu-id="4e681-155">Operations staff</span><span class="sxs-lookup"><span data-stu-id="4e681-155">Operations staff</span></span>

   - <span data-ttu-id="4e681-156">Regular core staff</span><span class="sxs-lookup"><span data-stu-id="4e681-156">Regular core staff</span></span>

   - <span data-ttu-id="4e681-157">Senior and strategic staff</span><span class="sxs-lookup"><span data-stu-id="4e681-157">Senior and strategic staff</span></span>

5. <span data-ttu-id="4e681-158">**선택** 을 클릭하고 **할당** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-158">Click **Select**, and then click **Assign**.</span></span>

6. <span data-ttu-id="4e681-159">브라우저에서 Azure Portal 탭을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-159">Close the Azure portal tab in your browser.</span></span>

## <a name="phase-3-add-your-user-accounts"></a><span data-ttu-id="4e681-160">3단계: 사용자 계정 추가</span><span class="sxs-lookup"><span data-stu-id="4e681-160">Phase 3: Add your user accounts</span></span>

<span data-ttu-id="4e681-161">이 단계에서는 정치적 캠페인에 대한 예제 사용자 계정을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-161">In this phase, you add the example user accounts for your political campaign.</span></span>

<span data-ttu-id="4e681-162">먼저 [Azure Active Directory PowerShell for Graph 모듈에 연결](../../enterprise/connect-to-microsoft-365-powershell.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-162">First, you [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md).</span></span>

<span data-ttu-id="4e681-163">다음으로 조직 이름, 사용자 위치 및 공통 암호를 입력합니다. PowerShell 명령 프롬프트 또는 ISE(Integrated Script Environment)에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-163">Next, you fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE):</span></span>

```powershell
$orgName="<organization name, such as contoso for the contoso.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$deptName="Senior and strategic staff"
$userNames=@("Candidate","ChiefOfStaff","Strategic1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="IT staff"
$userNames=@("ITAdmin1","ITAdmin2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Analytics staff"
$userNames=@("DataScientist1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Regular core staff"
$userNames=@("Regular1","Regular2")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Operations staff"
$userNames=@("Operations1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
$deptName="Field staff"
$userNames=@("FieldConsultant1")
foreach ($element in $userNames){ New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -Department $deptName -UsageLocation $location }
```

> [!IMPORTANT]
> <span data-ttu-id="4e681-p104">여기서는 개발/테스트 환경의 자동화 및 편리한 구성을 위해 공통된 암호를 사용합니다. 프로덕션 구독에서는 이 방식이 권장되지 않습니다. 이러한 각각의 새 사용자 계정으로 로그인하면 암호를 변경하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-p104">The use of a common password here is for automation and ease of configuration for a dev/test environment. This is not recommended for production subscriptions. As you sign in with each of these new user accounts, you will be prompted to change the password.</span></span>

<span data-ttu-id="4e681-167">다음 단계를 사용하여 동적 그룹 멤버 자격 및 그룹 기반 라이선스가 올바르게 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-167">Use these steps to verify that dynamic group membership and group-based licensing are working correctly.</span></span>

1. <span data-ttu-id="4e681-168">브라우저의 **Microsoft Office 홈** 탭에서 **관리** 타일을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-168">From the **Microsoft Office Home** tab of your browser, click the **Admin** tile.</span></span>

2. <span data-ttu-id="4e681-169">브라우저의 새 **Microsoft 365 관리 센터** 탭에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-169">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>

3. <span data-ttu-id="4e681-170">사용자 목록에서 **후보** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-170">In the list of users, click **Candidate**.</span></span>

4. <span data-ttu-id="4e681-171">**후보** 사용자 계정의 속성을 나열하는 창에서 다음을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-171">In the pane that lists the properties of the **Candidate** user account, verify that:</span></span>

   - <span data-ttu-id="4e681-172">**Senior and strategic staff** 그룹의 멤버인지 여부(**그룹 멤버 자격** 에서)</span><span class="sxs-lookup"><span data-stu-id="4e681-172">It is a member of the **Senior and strategic staff** group (in **Group memberships**).</span></span>

   - <span data-ttu-id="4e681-173">**Enterprise Mobility + Security E5** 및 **Office 365 Enterprise E5** 라이선스가 할당되었는지 여부(**제품 라이선스** 에서)</span><span class="sxs-lookup"><span data-stu-id="4e681-173">It has been assigned the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses (in **Product licenses**).</span></span>

5. <span data-ttu-id="4e681-174">**후보** 사용자 계정 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-174">Close the **Candidate** user account pane.</span></span>

## <a name="record-values-for-future-reference"></a><span data-ttu-id="4e681-175">나중에 참조하기 위해 값 기록</span><span class="sxs-lookup"><span data-stu-id="4e681-175">Record values for future reference</span></span>

<span data-ttu-id="4e681-176">이 개발/테스트 환경에 대해 Office 365 및 EMS 평가판 구독을 사용하려면 이러한 값을 기록해둡니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-176">Record these values for working with the Office 365 and EMS trial subscriptions for this dev/test environment:</span></span>

- <span data-ttu-id="4e681-177">평가판 구독 조직 이름: </span><span class="sxs-lookup"><span data-stu-id="4e681-177">Your trial subscription organization name:</span></span> ![Underline](../../media/Common-Images/TableLine.png)

  <span data-ttu-id="4e681-179">예를 들어 평가판 구독 도메인 이름 contoso.onmicrosoft.com의 경우 조직 이름은 "contoso"입니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-179">For example, for the trial subscription domain name of contoso.onmicrosoft.com, the organization name is "contoso".</span></span>

- <span data-ttu-id="4e681-180">전역 관리자 이름:</span><span class="sxs-lookup"><span data-stu-id="4e681-180">The global administrator name:</span></span> ![Underline](../../media/Common-Images/TableLine.png)<span data-ttu-id="4e681-182">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="4e681-182">.onmicrosoft.com</span></span>

  <span data-ttu-id="4e681-183">이 계정에 대한 암호와 다른 사용자 계정에 대한 일반적인 초기 암호를 안전한 위치에 기록해둡니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-183">Record the password for this account and the common initial password for the other user accounts in a secure location.</span></span>

## <a name="next-step"></a><span data-ttu-id="4e681-184">다음 단계</span><span class="sxs-lookup"><span data-stu-id="4e681-184">Next step</span></span>

<span data-ttu-id="4e681-185">[정치적 캠페인 개발/테스트 환경에서 팀 사이트 만들기](create-team-sites-in-a-political-campaign-dev-test-environment.md)를 사용하여 이 개발/테스트 환경에서 4가지 다른 유형의 SharePoint Online 팀 사이트를 구축합니다.</span><span class="sxs-lookup"><span data-stu-id="4e681-185">Build the four different types of SharePoint Online team sites in this dev/test environment with [Create team sites in a political campaign dev/test environment](create-team-sites-in-a-political-campaign-dev-test-environment.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4e681-186">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4e681-186">See also</span></span>

[<span data-ttu-id="4e681-187">정치적 캠페인, 비영리 조직 및 기타 기밀 조직에 대한 Microsoft 보안 지침</span><span class="sxs-lookup"><span data-stu-id="4e681-187">Microsoft Security Guidance for Political Campaigns, Nonprofits, and Other Agile Organizations</span></span>](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md)

[<span data-ttu-id="4e681-188">정치적 캠페인 개발/테스트 환경에서 팀 사이트 만들기</span><span class="sxs-lookup"><span data-stu-id="4e681-188">Create team sites in a political campaign dev/test environment</span></span>](create-team-sites-in-a-political-campaign-dev-test-environment.md)

[<span data-ttu-id="4e681-189">클라우드 도입 TLG(테스트 랩 가이드)</span><span class="sxs-lookup"><span data-stu-id="4e681-189">Cloud adoption Test Lab Guides (TLGs)</span></span>](../../enterprise/cloud-adoption-test-lab-guides-tlgs.md)

[<span data-ttu-id="4e681-190">클라우드 도입 및 하이브리드 솔루션</span><span class="sxs-lookup"><span data-stu-id="4e681-190">Cloud adoption and hybrid solutions</span></span>](/office365/enterprise/cloud-adoption-and-hybrid-solutions)