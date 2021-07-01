---
title: 개발/테스트 환경에서 보안 격리를 사용하여 팀 구성
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 08/14/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom: ''
description: 직원이 언제 어디서나 원격으로 작업할 수 있는 보안 및 인프라를 구성하세요.
ms.openlocfilehash: c58f0849937d7a807c9969e1651c51b3a9470ba5
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228606"
---
# <a name="configure-a-team-with-security-isolation-in-a-devtest-environment"></a><span data-ttu-id="b1067-103">개발/테스트 환경에서 보안 격리를 사용하여 팀 구성</span><span class="sxs-lookup"><span data-stu-id="b1067-103">Configure a team with security isolation in a dev/test environment</span></span>

<span data-ttu-id="b1067-104">이 문서에서는 개발/테스트 환경에서 [보안 격리](secure-teams-security-isolation.md)를 사용하여 팀을 만들기 위한 단계별 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-104">This article provides step-by-step instructions to create a [team with security isolation](secure-teams-security-isolation.md) in a dev/test environment.</span></span>

![회사 전략 격리 팀 구성](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

<span data-ttu-id="b1067-106">이 개발/테스트 환경을 사용하여 생산에 이러한 유형의 팀을 배포하기 전에 특정 요구 사항에 맞게 설정을 시험해 보고 세부 조정하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-106">Use this dev/test environment to experiment and fine-tune settings for your specific needs before deploying this type of team in production.</span></span>

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="b1067-107">1단계: Microsoft 365 Enterprise 테스트 환경 구축</span><span class="sxs-lookup"><span data-stu-id="b1067-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="b1067-108">최소 요구 사항을 사용하여 중요하고 매우 중요한 팀을 간단한 방식으로 테스트하려는 경우에는 [간단한 기반 구성](../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-108">If you just want to test sensitive and highly sensitive teams in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](../enterprise/lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>

<span data-ttu-id="b1067-109">시뮬레이션 된 엔터프라이즈에서 중요하고 매우 중요한 팀을 테스트하려면 [암호 해시 동기화](../enterprise/password-hash-sync-m365-ent-test-environment.md)의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-109">If you want to test sensitive and highly sensitive teams in a simulated enterprise, follow the instructions in [Password hash synchronization](../enterprise/password-hash-sync-m365-ent-test-environment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="b1067-110">보안 격리를 사용하여 팀을 테스트할 때는 인터넷에 연결된 시뮬레이트된 인트라넷 및 AD DS(Active Directory 도메인 서비스) 포리스트의 디렉터리 동기화를 포함하여 시뮬레이트된 엔터프라이즈 테스트 환경이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-110">Testing a team with security isolation does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="b1067-111">보안 격리를 사용하여 팀을 테스트하고 일반적인 조직을 나타내는 환경에서 테스트할 수 있도록 여기에 옵션으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-111">It is provided here as an option so that you can test a team with security isolation and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-create-and-configure-your-azure-active-directory-azure-ad-group-and-users"></a><span data-ttu-id="b1067-112">2단계: Azure AD(Azure Active Directory) 그룹 및 사용자 만들기 및 구성</span><span class="sxs-lookup"><span data-stu-id="b1067-112">Phase 2: Create and configure your Azure Active Directory (Azure AD) group and users</span></span>

<span data-ttu-id="b1067-113">이 단계에서는 가상의 조직에 대한 Azure AD 그룹 및 사용자를 만들고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-113">In this phase, you create and configure an Azure AD group and users for your fictional organization.</span></span>

<span data-ttu-id="b1067-114">먼저 Azure 포털을 사용하여 보안 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-114">First, create a security group with the Azure portal.</span></span>

1. <span data-ttu-id="b1067-115">브라우저에 별도의 탭을 만든 다음 [https://portal.azure.com](https://portal.azure.com)에서 Azure Portal로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-115">Create a separate tab in your browser, and then go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span> <span data-ttu-id="b1067-116">필요한 경우 Office 365 E5 평가판 혹은 유료 구독의 전역 관리자 계정의 자격 증명으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-116">If needed, sign in with the credentials of the global administrator account for your Microsoft 365 E5 trial or paid subscription.</span></span>

2. <span data-ttu-id="b1067-117">Azure Portal에서 **Azure Active Directory > 그룹** 을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-117">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>

3. <span data-ttu-id="b1067-118">**그룹 - 모든 그룹** 블레이드에서 **+ 새 그룹** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-118">On the **Groups - All groups** blade, click **+ New group**.</span></span>

4. <span data-ttu-id="b1067-119">**그룹** 블레이드에서:</span><span class="sxs-lookup"><span data-stu-id="b1067-119">On the **Group** blade:</span></span>

  - <span data-ttu-id="b1067-120">**그룹 유형** 에서 **보안** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-120">Select **Security** in **Group type**.</span></span>

  - <span data-ttu-id="b1067-121">**이름** 에 **C-Suite** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-121">Type **C-Suite** in **Name**.</span></span>

  - <span data-ttu-id="b1067-122">**멤버 유형** 에서 **할당됨** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-122">Select **Assigned** in **Membership type**.</span></span>

5. <span data-ttu-id="b1067-123">**만들기** 를 클릭한 다음 **그룹** 블레이드를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-123">Click **Create**, and then close the **Group** blade.</span></span>

<span data-ttu-id="b1067-124">그런 다음 새 **C-제품군** 그룹의 구성원에게 Microsoft 365 E5 라이선스가 자동으로 할당되도록 자동 라이선스를 구성하세요.</span><span class="sxs-lookup"><span data-stu-id="b1067-124">Next, configure automatic licensing so that members of the new **C-Suite** group are automatically assigned a Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="b1067-125">Azure Portal에서 **Azure Active Directory > 라이선스 > 모든 제품** 을 차례로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-125">In the Azure portal, click **Azure Active Directory > Licenses > All products**.</span></span>

2. <span data-ttu-id="b1067-126">목록에서 **Microsoft 365 Enterprise E5** 를 선택한 다음 **할당** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-126">In the list, select **Microsoft 365 Enterprise E5**, and then click **Assign**.</span></span>

3. <span data-ttu-id="b1067-127">**라이선스 할당** 블레이드에서 **사용자 및 그룹** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-127">In the **Assign license** blade, click **Users and groups**.</span></span>

4. <span data-ttu-id="b1067-128">그룹 목록에서 **C-제품군** 그룹을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-128">In the list of groups, select the **C-Suite** group.</span></span>

5. <span data-ttu-id="b1067-129">**선택** 을 클릭하고 **할당** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-129">Click **Select**, and then click **Assign**.</span></span>

6. <span data-ttu-id="b1067-130">브라우저에서 Azure Portal 탭을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-130">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="b1067-131">그런 다음, [Azure Active Directory PowerShell for Graph 모듈에 연결](../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-131">Next, [connect with the Azure Active Directory PowerShell for Graph module](../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="b1067-132">조직 이름, 사용자 위치 및 공통 암호를 입력한 다음 PowerShell 명령 프롬프트 또는 ISE(Integrated Script Environment)에서 다음 명령을 실행하여 새로운 사용자 계정을 만들고 C-제품군 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-132">Fill in your organization name, your location, and a common password, and then run these commands from the PowerShell command prompt or Integrated Script Environment (ISE) to create new user accounts and add them to the C-Suite group:</span></span>

```powershell
$orgName="<organization name, such as contoso-test for the contoso-test.onmicrosoft.com trial subscription domain name>"
$location="<the ISO ALPHA2 country code, such as US for the United States>"
$commonPassword="<common password for all the new accounts>"

$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPassword

$groupName="C-Suite"
$userNames=@("CEO","CFO","CIO")
$groupID=(Get-AzureADGroup | Where { $_.DisplayName -eq $groupName }).ObjectID
ForEach ($element in $userNames){
New-AzureADUser -DisplayName $element -PasswordProfile $PasswordProfile -UserPrincipalName ($element + "@" + $orgName + ".onmicrosoft.com") -AccountEnabled $true -MailNickName $element -UsageLocation $location
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $element }).ObjectID -ObjectId $groupID
}
```

> [!NOTE]
> <span data-ttu-id="b1067-p103">여기서 공통 암호를 사용하는 것은 자동화 및 개발/테스트 환경에 대한 구성 용이성을 위한 것입니다. 프로덕션 구독에는 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-p103">The use of a common password here is for automation and ease of configuration for a dev/test environment. Obviously, this is highly discouraged for production subscriptions.</span></span>

<span data-ttu-id="b1067-135">이러한 단계에 따라 그룹 기반 라이선스가 제대로 작동하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-135">Use these steps to verify that group-based licensing is working correctly.</span></span>

1. <span data-ttu-id="b1067-136">[Microsoft 365 관리 센터](https://admin.microsoft.com)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-136">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>

2. <span data-ttu-id="b1067-137">브라우저의 새 **Microsoft 365 관리 센터** 탭에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-137">From the new **Microsoft 365 admin center** tab of your browser, click **Users**.</span></span>

3. <span data-ttu-id="b1067-138">사용자 목록에서 **CEO** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-138">In the list of users, click **CEO**.</span></span>

4. <span data-ttu-id="b1067-139">**CEO** 사용자 계정의 속성을 나열하는 창에서(**제품 라이선스** 에서) **Microsoft 365 Enterprise E5** 라이선스가 할당되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-139">In the pane that lists the properties of the **CEO** user account, verify that it has been assigned the **Microsoft 365 Enterprise E5** license in **Product licenses**.</span></span>

## <a name="phase-3-create-your-team"></a><span data-ttu-id="b1067-140">3단계: 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="b1067-140">Phase 3: Create your team</span></span>

<span data-ttu-id="b1067-141">이 단계에서는 시니어 리더십 팀의 구성원이 회사 전략에 대해 협업할 수 있도록 보안 격리 기능이 있는 팀을 작성하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-141">In this phase, you create and configure a team with security isolation for members of the senior leadership team to collaborate on company strategy.</span></span>

<span data-ttu-id="b1067-142">먼저 [이 문서](../compliance/sensitivity-labels-teams-groups-sites.md)의 단계를 진행하기 전에 민감도 레이블을 사용하여 Microsoft Teams, Office 365 그룹 ​​및 SharePoint 사이트의 콘텐츠를 보호하세요.</span><span class="sxs-lookup"><span data-stu-id="b1067-142">First, enable sensitivity labels to protect content in Microsoft Teams, Office 365 groups, and SharePoint sites before you proceed with the steps in [this article](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span>

<span data-ttu-id="b1067-143">그런 다음, 팀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-143">Next, create the team:</span></span>

1. <span data-ttu-id="b1067-144">Teams에서 앱 왼쪽에 있는 **Teams** 를 클릭한 다음, 팀 목록 아래에서 **팀 참가 또는 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-144">In Teams, click **Teams** on the left side of the app, then click **Join or create a team** at the bottom of the teams list.</span></span>
2. <span data-ttu-id="b1067-145">**팀 만들기** 를 클릭합니다(첫 번째 카드, 왼쪽 위 모서리).</span><span class="sxs-lookup"><span data-stu-id="b1067-145">Click **Create team** (first card, top left corner).</span></span>
3. <span data-ttu-id="b1067-146">**처음부터 팀 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-146">Choose **Build a team from scratch**.</span></span>
4. <span data-ttu-id="b1067-147">**민감도** 목록에서 기본값을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-147">In the **Sensitivity** list, keep the default.</span></span>
5. <span data-ttu-id="b1067-148">**개인 정보 보호** 에서 **비공개** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-148">Under **Privacy**, click **Private**.</span></span>
6. <span data-ttu-id="b1067-149">**회사 전략** 을 입력한 다음 **만들기** > **닫기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-149">Type **Company Strategy**, and then click **Create** > **Close**.</span></span>

<span data-ttu-id="b1067-150">다음으로, 회사 전략 그룹의 소유자에게 개인 채널 만들기를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-150">Next, restrict the creation of private channels to owners of the Company Strategy group.</span></span>

1. <span data-ttu-id="b1067-151">팀에서 **추가 옵션** 을 클릭한 다음 **팀 관리** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-151">In the team, click **More options**, and then click **Manage team**.</span></span>
2. <span data-ttu-id="b1067-152">**설정** 탭에서 **구성원 사용 권한** 을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-152">On the **Settings** tab, expand **Member permissions**.</span></span>
3. <span data-ttu-id="b1067-153">**구성원이 비공개 채널을 만들 수 있도록 허용** 확인란을 선택 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-153">Clear the **Allow members to create private channels** check box.</span></span>

<span data-ttu-id="b1067-154">다음으로, 다음 설정으로 민감도 레이블을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-154">Next, you need to configure a sensitivity label with the following settings:</span></span>

- <span data-ttu-id="b1067-155">이름을 회사 전략이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-155">The name is Company Strategy</span></span>
- <span data-ttu-id="b1067-156">암호화가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-156">Encryption is enabled</span></span>
- <span data-ttu-id="b1067-157">회사 전략 그룹은 공동 작성자 권한이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-157">The Company Strategy group has Co-Author permissions</span></span>

<span data-ttu-id="b1067-158">다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-158">Follow these steps:</span></span>

1. <span data-ttu-id="b1067-159">[Microsoft 365 규정 준수 센터](https://compliance.microsoft.com)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-159">Open the [Microsoft 365 compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="b1067-160">**솔루션** 에서 **정보 보호** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-160">Under **Solutions**, click **Information protection**.</span></span>
3. <span data-ttu-id="b1067-161">**레이블 만들기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-161">Click **Create a label**.</span></span>
4. <span data-ttu-id="b1067-162">레이블 이름에 대한 **회사 전략** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-162">Type **Company Strategy** for the label name.</span></span>
5. <span data-ttu-id="b1067-163">툴팁으로 **선임 리더십 회사 전략 문서** 를 입력한 다음 **다음** 을 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="b1067-163">Type **Senior leadership company strategy documents** as the tool tip, and then click **Next**.</span></span>
6. <span data-ttu-id="b1067-164">**암호화** 페이지의 **암호화** 드롭다운에서 **적용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-164">On the **Encryption** page, in the **Encryption** dropdown, choose **Apply**.</span></span>
7. <span data-ttu-id="b1067-165">팀 사용 권한을 추가하려면:</span><span class="sxs-lookup"><span data-stu-id="b1067-165">To add the team permissions:</span></span><br>
  <span data-ttu-id="b1067-166">a.</span><span class="sxs-lookup"><span data-stu-id="b1067-166">a.</span></span> <span data-ttu-id="b1067-167">**사용 권한 할당** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-167">Click **Assign permissions**.</span></span><br>
  <span data-ttu-id="b1067-168">b.</span><span class="sxs-lookup"><span data-stu-id="b1067-168">b.</span></span> <span data-ttu-id="b1067-169">**사용자 또는 그룹 추가** 를 클릭하고 **회사 전략** 을 선택한 다음 **추가** 를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="b1067-169">Click **Add users or groups**, select **Company Strategy**, and then click **Add**.</span></span><br>
  <span data-ttu-id="b1067-170">c.</span><span class="sxs-lookup"><span data-stu-id="b1067-170">c.</span></span> <span data-ttu-id="b1067-171">**사용 권한 선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-171">Click **Choose permissions**.</span></span><br>
  <span data-ttu-id="b1067-172">d.</span><span class="sxs-lookup"><span data-stu-id="b1067-172">d.</span></span> <span data-ttu-id="b1067-173">드롭다운 목록에서 **공동 작성** 을 선택한 다음 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-173">Choose **Co-Author** from the dropdown list, and then click **Save**.</span></span><br>
8. <span data-ttu-id="b1067-174">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-174">Click **Next**.</span></span>
9. <span data-ttu-id="b1067-175">**콘텐츠 표시** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-175">On the **Content marking** page, click **Next**.</span></span>
10. <span data-ttu-id="b1067-176">**사이트 및 그룹 설정** 페이지에서 **사이트 및 그룹 설정** 을 **켜짐** 으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-176">On the **Site and group settings** page, set **Site and group settings** to **On**.</span></span>
11. <span data-ttu-id="b1067-177">**Office 365 그룹에 연결된 팀 사이트의 개인 정보 보호** 드롭다운에서 **비공개 - 구성원만 사이트에 액세스할 수 있음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-177">In the **Privacy of Office 365 group-connected team sites** dropdown, choose **Private - only members can access the site**.</span></span>
12. <span data-ttu-id="b1067-178">**관리되지 않는 장치** 에서 **액세스 차단** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-178">Under **Unmanaged devices**, choose **Block access**.</span></span>
13. <span data-ttu-id="b1067-179">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-179">Click **Next**.</span></span>
14. <span data-ttu-id="b1067-180">**Office 앱에 대한 자동 레이블 지정** 페이지에서 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-180">On the **Auto-labeling for Office apps** page, click **Next**.</span></span>
15. <span data-ttu-id="b1067-181">**제출** 을 클릭한 다음 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-181">Click **Submit**, and then click **Done**.</span></span>

<span data-ttu-id="b1067-182">다음 단계에 따라 새 레이블을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-182">Next, publish the new label with these steps:</span></span>

1. <span data-ttu-id="b1067-183">Microsoft 365 규정 준수 센터의 **정보 보호** 페이지에서 **레이블 정책** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-183">In the Microsoft 365 compliance center, on the **Information protection** page, choose the **Label policies** tab.</span></span>
2. <span data-ttu-id="b1067-184">**레이블 게시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-184">Click **Publish labels**.</span></span>
3. <span data-ttu-id="b1067-185">**민감도 레이블을 게시하도록 선택** 페이지에서 **민감도 레이블을 게시하도록 선택** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-185">On the **Choose sensitivity labels to publish** page, click **Choose sensitivity labels to publish**.</span></span>
4. <span data-ttu-id="b1067-186">**회사 전략** 을 선택한 다음 **추가** 를 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="b1067-186">Select **Company Strategy**, and then click **Add**.</span></span>
5. <span data-ttu-id="b1067-187">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-187">Click **Next**.</span></span>
6. <span data-ttu-id="b1067-188">**사용자 및 그룹에 게시** 페이지에서 **사용자 및 그룹 선택** 을 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="b1067-188">On the **Publish to users and groups** page, click **Choose users and groups**.</span></span>
7. <span data-ttu-id="b1067-189">**추가** 를 클릭한 다음 **회사 전략** 을 선택하세요.</span><span class="sxs-lookup"><span data-stu-id="b1067-189">Click **Add**, and then select **Company Strategy**.</span></span>
8. <span data-ttu-id="b1067-190">**추가** 를 클릭한 다음 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-190">Click **Add**, and then click **Done**.</span></span>
9. <span data-ttu-id="b1067-191">**다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-191">Click **Next**.</span></span>
10. <span data-ttu-id="b1067-192">정책 설정 페이지에서 **사용자가 레이블이나 하위 분류 레이블을 제거하려면 정당성을 제공해야 함** 확인란을 선택한 후 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-192">On the Policy settings page, select the **Users must provide justification to remove a label or lower classification label** check box, and then click **Next**.</span></span>
11. <span data-ttu-id="b1067-193">정책 이름에 대 한 **회사 전략** 를 입력하고 **다음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-193">Type **Company Strategy** for the policy name, and then click **Next**.</span></span>
12. <span data-ttu-id="b1067-194">**제출** 을 클릭한 다음 **완료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-194">Click **Submit** and then click **Done**.</span></span>

<span data-ttu-id="b1067-195">**회사 전략** 레이블이 게시 된 후 사용할 수 있기까지 시간이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-195">It may take some time for the **Company Strategy** label to become available after it's been published.</span></span>

<span data-ttu-id="b1067-196">그런 다음 새 라벨을 **회사 전략** 팀에 적용하고 기본 공유 링크 유형을 업데이트하여 의도하지 않은 것보다 더 많은 사용자가 파일 및 폴더를 실수로 공유할 위험을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-196">Next, apply your new label to the **Company Strategy** team and update the default sharing link type to reduce the risk of accidentally sharing files and folders to a wider audience than intended.</span></span>

1. <span data-ttu-id="b1067-197">[SharePoint 관리 센터](https://admin.microsoft.com/sharepoint)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-197">Open the [SharePoint admin center](https://admin.microsoft.com/sharepoint).</span></span>
2. <span data-ttu-id="b1067-198">**사이트** 에서 **활성 사이트** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-198">Under **Sites**, click **Active sites**.</span></span>
3. <span data-ttu-id="b1067-199">**회사 전략** 사이트를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-199">Click the **Company Strategy** site.</span></span>
4. <span data-ttu-id="b1067-200">**정책** 탭의 **민감도** 에서 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-200">On the **Policies** tab, under **Sensitivity**, click **Edit**.</span></span>
5. <span data-ttu-id="b1067-201">**회사 전략** 레이블을 선택한 다음 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-201">Select the **Company Strategy** label, and then click **Save**.</span></span>
6. <span data-ttu-id="b1067-202">**정책** 탭의 **외부 공유** 에서 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-202">On the **Policies** tab, under **External sharing**, click **Edit**.</span></span>
5. <span data-ttu-id="b1067-203">**조직 내부 사용자만** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-203">Choose **Only people in your organization**.</span></span>
6. <span data-ttu-id="b1067-204">**기본 공유** 링크 유형에서 **조직 수준 설정과 동일** 확인란을 선택 취소하고 **기존 액세스가 있는 사용자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-204">Under **Default sharing** link type, clear the **Same as organization-level setting** check box, and select **People with existing access**.</span></span>
7. <span data-ttu-id="b1067-205">**저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-205">Click **Save**.</span></span>

<span data-ttu-id="b1067-206">그런 다음 **회사 전략** 팀에 대한 소유자 전용 사이트 공유를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-206">Next, configure owners-only site sharing for the **Company Strategy** team.</span></span>

1. <span data-ttu-id="b1067-207">Teams에서 **회사 전략** 팀의 **일반** 탭으로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="b1067-207">In Teams, navigate to the **General** tab of the **Company Strategy** team.</span></span>
2. <span data-ttu-id="b1067-208">팀의 도구 막대에서 **파일** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-208">In the tool bar for the team, click **Files**.</span></span>
3. <span data-ttu-id="b1067-209">줄임표를 클릭한 다음 **SharePoint에서 열기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-209">Click the ellipsis, and then click **Open in SharePoint**.</span></span>
4. <span data-ttu-id="b1067-210">기본 SharePoint 사이트의 도구 막대에서 설정 아이콘을 클릭한 다음 **사이트 사용 권한** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-210">In the tool bar of the underlying SharePoint site, click the settings icon, and then click **Site permissions**.</span></span>
5. <span data-ttu-id="b1067-211">사이트 권한 창의 **사이트 공유** 에서 **멤버 공유 방법 변경** 을 클릭하세요.</span><span class="sxs-lookup"><span data-stu-id="b1067-211">In the Site permissions pane, under **Site Sharing**, click **Change how members can share**.</span></span>
6. <span data-ttu-id="b1067-212">**사용 권한 공유** 에서 **사이트 소유자만 파일, 폴더 및 사이트를 공유할 수 있습니다** 를 선택하고 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-212">Under **Sharing permissions**, choose **Only site owners can share files, folders, and the site**, and then click **Save**.</span></span>
7. <span data-ttu-id="b1067-213">**사용 권한** 과 **설정 창** 을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-213">Close the **Permissions** and **Settings** panes.</span></span>

<span data-ttu-id="b1067-214">회사 전략 그룹의 구성원으로 로그인하면 Word, Excel 및 PowerPoint의 홈 도구 모음에있는 **민감도** 옵션에 **회사 전략** 이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-214">If you sign in as a member of the Company Strategy group, you will see **Company Strategy** in the **Sensitivity** option in the Home toolbar of Word, Excel, and PowerPoint.</span></span> <span data-ttu-id="b1067-215">**중요** 옵션에서 **회사 전략 레이블** 을 선택하여 레이블을 파일에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-215">Select the **Company Strategy** label from the **Sensitivity** option to assign the label to a file.</span></span>

<span data-ttu-id="b1067-216">다음은 회사 전략 팀에 대한 구성의 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="b1067-216">Here is the resulting configuration for the Company Strategy team.</span></span>

![회사 전략 격리 팀 구성](../media/team-security-isolation-dev-test/team-security-isolation-dev-test-config.png)

## <a name="next-step"></a><span data-ttu-id="b1067-218">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b1067-218">Next step</span></span>

<span data-ttu-id="b1067-219">프로덕션 배포 준비가 되면 [구성 지침](secure-teams-security-isolation.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b1067-219">When you're ready for production deployment, see these [configuration instructions](secure-teams-security-isolation.md).</span></span>
