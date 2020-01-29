---
title: Office 365에서 불법 동의 권한 부여 검색 및 교정
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
description: Office 365에서 불법 동의 권한 부여 공격을 인식하고 교정하는 방법에 대해 알아보세요.
ms.openlocfilehash: ae26656cdfcb6f17bbe4caa1016f6428f3bd655e
ms.sourcegitcommit: 3f8957ddd04b8710bb5f314a0902fdee50c7c9b7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "41572995"
---
# <a name="detect-and-remediate-illicit-consent-grants-in-office-365"></a><span data-ttu-id="4b501-103">Office 365에서 불법 동의 권한 부여 검색 및 교정</span><span class="sxs-lookup"><span data-stu-id="4b501-103">Detect and Remediate Illicit Consent Grants in Office 365</span></span>

<span data-ttu-id="4b501-104">**요약** Office 365에서 불법 동의 권한 부여 공격을 인식하고 교정하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="4b501-104">**Summary**  Learn how to recognize and remediate the illicit consent grants attack in Office 365.</span></span>

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a><span data-ttu-id="4b501-105">Office 365에서 불법 동의 권한 부여 공격은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="4b501-105">What is the illicit consent grant attack in Office 365?</span></span>

<span data-ttu-id="4b501-106">불법 동의 권한 부여 공격에는 공격자가 연락처 정보, 전자 메일 또는 문서 등의 데이터에 대한 액세스를 요청하는 Azure 등록 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-106">In an illicit consent grant attack, the attacker creates an Azure-registered application that requests access to data such as contact information, email, or documents.</span></span> <span data-ttu-id="4b501-107">그런 다음 공격자는 최종 사용자가 피싱 공격을 통해 또는 신뢰할 수있는 웹 사이트에 불법 코드를 주입하여 해당 응용 프로그램에 데이터 액세스 권한을 부여하도록 속임수를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-107">The attacker then tricks an end user into granting that application consent to access their data either through a phishing attack, or by injecting illicit code into a trusted website.</span></span> <span data-ttu-id="4b501-108">불법 응용 프로그램에 대한 동의가 부여되면 조직 계정이 없어도 데이터에 대한 계정 수준의 액세스 권한을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-108">After the illicit application has been granted consent, it has account-level access to data without the need for an organizational account.</span></span> <span data-ttu-id="4b501-109">침해된 계정에 대한 암호를 재설정하거나 계정에 MFA(다단계 인증)을 요구하는 등의 일반적인 조치 단계는 이러한 응용 프로그램이 타사 응용 프로그램이므로 조직 외부에 있기 때문에 이 유형의 공격에 효과적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-109">Normal remediation steps, like resetting passwords for breached accounts or requiring Multi-Factor Authentication (MFA) on accounts, are not effective against this type of attack, since these are third-party applications and are external to the organization.</span></span> <span data-ttu-id="4b501-110">이러한 공격은 정보를 호출하는 엔터티가 사용자가 아니라 자동화임을 가정하는 상호 작용 모델을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-110">These attacks leverage an interaction model which presumes the entity that is calling the information is automation and not a human.</span></span>

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a><span data-ttu-id="4b501-111">불법 동의 권한 부여는 Office 365에서 어떻게 보이나요?</span><span class="sxs-lookup"><span data-stu-id="4b501-111">What does an illicit consent grant attack look like in Office 365?</span></span>

<span data-ttu-id="4b501-112">이 공격의 IOC(침해 지표)라고도 하는 신호를 찾으려면 Office 365 **감사 로그**를 검색해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-112">You need to search the Office 365 **audit log** to find signs, also called Indicators of Compromise (IOC) of this attack.</span></span> <span data-ttu-id="4b501-113">여러 Azure 등록 응용 프로그램 및 대규모 사용자를 포함하는 조직의 경우 가장 좋은 방법은 주 단위로 조직 동의 권한 부여를 검토하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-113">For organizations with many Azure-registered applications and a large user base, the best practice is to review your organizations consent grants on a weekly basis.</span></span>

### <a name="steps-for-finding-signs-of-this-attack"></a><span data-ttu-id="4b501-114">이 공격의 신호를 찾는 단계</span><span class="sxs-lookup"><span data-stu-id="4b501-114">Steps for finding signs of this attack</span></span>

1. <span data-ttu-id="4b501-115">Office 365 테넌트에서 **보안 및 준수 센터**를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-115">Open the **Security and Compliance Center** in your Office 365 tenant.</span></span>

2. <span data-ttu-id="4b501-116">**검색 및 조사** 노드로 이동하고 **감사 로그** 검색을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-116">Navigate to the **Search & investigation** node and select **audit log** search.</span></span>

3. <span data-ttu-id="4b501-117">검색(모든 활동 및 모든 사용자)을 만들고, 응용 프로그램에 대한 동의 결과를 필터링하고, OAuth2PermissionGrant를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-117">Create a search (all activities and all users) and filter the results for Consent to application, and Add OAuth2PermissionGrant.</span></span>

4. <span data-ttu-id="4b501-118">확장 속성을 확인하고 IsAdminContent가 True로 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-118">Examine the Extended Properties and check to see if IsAdminContent is set to True.</span></span>

> [!NOTE]
> <span data-ttu-id="4b501-p103">• 검색 결과에 해당 감사 로그 항목이 표시되려면 이벤트 발생 시점으로부터 30분에서 24시간 정도 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-p103">• It can take up to 30 minutes or up to 24 hours after an event occurs for the corresponding audit log entry to be displayed in the search results. </span></span><br/><br/> <span data-ttu-id="4b501-120">• 감사 기록이 보존되고 감사 로그에서 검색 가능한 시간은 Office 365 구독, 특히 특정 사용자에게 할당된 라이선스 유형에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-120">• The length of time that an audit record is retained and searchable in the audit log depends on your Office 365 subscription, and specifically the type of the license that is assigned to a specific user.</span></span> <span data-ttu-id="4b501-121">자세한 내용은 [감사 로그](../../compliance/search-the-audit-log-in-security-and-compliance.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4b501-121">For more information, see [Audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>
<span data-ttu-id="4b501-122">이 값이 true이면 전역 관리자 액세스 권한이 있는 사용자가 데이터에 대한 광범위한 액세스 권한을 부여할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-122">If this value is true, it indicates that someone with Global Administrator access may have granted broad access to data.</span></span> <span data-ttu-id="4b501-123">예기치 않은 상황이라면 [공격을 확인](#how-to-confirm-an-attack)하는 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="4b501-123">If this is unexpected, take steps to [confirm an attack](#how-to-confirm-an-attack).</span></span>

## <a name="how-to-confirm-an-attack"></a><span data-ttu-id="4b501-124">공격을 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="4b501-124">How to confirm an attack</span></span>

<span data-ttu-id="4b501-125">위에 나와 있는 IOCs의 인스턴스가 하나 이상 있는 경우 공격이 발생했음을 확실하게 확인하도록 추가 조사를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-125">If you have one or more instances of the IOCs listed above, you need to do further investigation to positively confirm that the attack occurred.</span></span> <span data-ttu-id="4b501-126">다음의 세 가지 방법 중 하나를 사용하여 공격을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-126">You can use any of these three methods to confirm the attack.</span></span>

- <span data-ttu-id="4b501-127">Azure Active Directory 포털을 사용하는 인벤터리 응용 프로그램과 해당 사용 권한</span><span class="sxs-lookup"><span data-stu-id="4b501-127">Inventory applications and their permissions using the Azure Active Directory portal.</span></span> <span data-ttu-id="4b501-128">이 방법은 철저하지만 한번에 한 명의 사용자만 검사할 수 있어 검사할 사용자가 많은 경우에는 막대한 시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-128">This method is thorough, but you can only check one user at a time which can be very time consuming if you have many users to check.</span></span>

- <span data-ttu-id="4b501-129">PowerShell을 사용하는 인벤터리 응용 프로그램과 해당 사용 권한</span><span class="sxs-lookup"><span data-stu-id="4b501-129">Inventory applications and their permissions using PowerShell.</span></span> <span data-ttu-id="4b501-130">이 방법은 최소한의 오버 헤드를 사용하는 가장 빠르고 철저한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-130">This is the fastest and most thorough method, with the least amount of overhead.</span></span>

- <span data-ttu-id="4b501-131">사용자가 앱과 권한을 개별적으로 확인하고 조치를 위해 그 결과를 관리자에게 다시 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-131">Have your users individually check their apps and permissions and report the results back to the administrators for remediation.</span></span>

## <a name="inventory-apps-with-access-in-your-organization"></a><span data-ttu-id="4b501-132">조직에서 액세스 권한이 있는 인벤터리 앱</span><span class="sxs-lookup"><span data-stu-id="4b501-132">Inventory apps with access in your organization</span></span>

<span data-ttu-id="4b501-133">Azure Active Directory 포털이나 PowerShell을 사용하여 사용자를 위해 이 작업을 수행하거나 사용자가 응용 프로그램 액세스를 개별적으로 열거하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-133">You can do this for your users with either the Azure Active Directory Portal, or PowerShell or have your users individually enumerate their application access.</span></span>

### <a name="steps-for-using-the-azure-active-directory-portal"></a><span data-ttu-id="4b501-134">Azure Active Directory 포털 사용 단계</span><span class="sxs-lookup"><span data-stu-id="4b501-134">Steps for using the Azure Active Directory Portal</span></span>

<span data-ttu-id="4b501-135">[Azure Active Directory 포털](https://portal.azure.com/)를 사용하여 개별 사용자에게 사용 권한을 부여한 응용 프로그램을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-135">You can look up the applications to which any individual user has granted permissions by using the [Azure Active Directory Portal](https://portal.azure.com/).</span></span>

1. <span data-ttu-id="4b501-136">관리 권한으로 Azure Portal에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-136">Sign in to the Azure Portal with administrative rights.</span></span>

2. <span data-ttu-id="4b501-137">Azure Active Directory 블레이드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-137">Select the Azure Active Directory blade.</span></span>

3. <span data-ttu-id="4b501-138">**사용자**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-138">Select **Users**.</span></span>

4. <span data-ttu-id="4b501-139">검토할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-139">Select the user that you want to review.</span></span>

5. <span data-ttu-id="4b501-140">**응용 프로그램**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-140">Select **Applications**.</span></span>

<span data-ttu-id="4b501-141">사용자에게 할당된 앱과 응용 프로그램이 보유한 사용 권한이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-141">This will show you the apps that are assigned to the user and what permissions the applcations have.</span></span>

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a><span data-ttu-id="4b501-142">사용자가 응용 프로그램에 액세스를 열거하도록 하는 단계</span><span class="sxs-lookup"><span data-stu-id="4b501-142">Steps for having your users enumerate their application access</span></span>

<span data-ttu-id="4b501-143">사용자가 https://myapps.microsoft.com(으)로 이동하여 해당 응용 프로그램에 대한 액세스를 검토할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-143">Have your users go to https://myapps.microsoft.com and review their own application access there.</span></span> <span data-ttu-id="4b501-144">액세스 권한이 있는 모든 앱을 확인하고, 세부 정보를 볼 수 있습니다(액세스 범위 포함). 또는 의심스러운 앱이나 불법 앱에 대한 사용 권한을 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-144">They should be able to see all the apps with access, view details about them (including the scope of access), and be able to revoke privileges to suspicious or illicit apps.</span></span>

### <a name="steps-for-doing-this-with-powershell"></a><span data-ttu-id="4b501-145">PowerShell로 이 작업을 수행하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="4b501-145">Steps for doing this with PowerShell</span></span>

<span data-ttu-id="4b501-146">불법 동의 권한 부여를 확인하는 가장 간단한 방법은 [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)을 실행하는 것입니다. 이는 테넌시의 모든 사용자에 대한 모든 OAuth 동의 권한 부여 및 OAuth 앱을 하나의 .csv 파일로 덤프합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-146">The simplest way to verify the Illicit Consent Grant attack is to run [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), which will dump all the OAuth consent grants and OAuth apps for all users in your tenancy into one .csv file.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="4b501-147">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4b501-147">Pre-requisites</span></span>

- <span data-ttu-id="4b501-148">Azure AD PowerShell 라이브러리가 설치됨</span><span class="sxs-lookup"><span data-stu-id="4b501-148">The Azure AD PowerShell library installed.</span></span>

- <span data-ttu-id="4b501-149">스크립트를 실행할 테넌트에 대한 전역 관리자 권한</span><span class="sxs-lookup"><span data-stu-id="4b501-149">Global administrator rights on the tenant that the script will be run against.</span></span>

- <span data-ttu-id="4b501-150">스크립트를 실행할 컴퓨터의 로컬 관리자</span><span class="sxs-lookup"><span data-stu-id="4b501-150">Local Administrator on the computer from which will run the scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4b501-151">모든 관리 계정에 대해 MFA(다단계 인증)을 요구하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-151">We highly recommend that you require multi-factor authentication on your administrative account.</span></span> <span data-ttu-id="4b501-152">이 스크립트는 MFA 인증을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-152">This script supports MFA authentication.</span></span>

1. <span data-ttu-id="4b501-153">로컬 관리자 권한으로 스크립트를 실행할 컴퓨터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-153">Sign in to the computer that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="4b501-154">GitHub에서 [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) 스크립트를 스크립트를 실행할 폴더로 다운로드하거나 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-154">Download or copy the [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script from GitHub to a folder from which you will run the scruipt.</span></span> <span data-ttu-id="4b501-155">이 폴더는 "permissions.csv" 출력 파일이 작성되는 폴더와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-155">This will be the same folder to which the output "permissions.csv" file will be written.</span></span>

3. <span data-ttu-id="4b501-156">PowerShell 인스턴스를 관리자로 열고 스크립트를 저장한 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-156">Open a PowerShell instance as an administrator and open to the folder you saved the script to.</span></span>

4. <span data-ttu-id="4b501-157">[Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread) cmdlet을 사용하여 디렉터리에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-157">Connect to your directory using the [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread) cmdlet.</span></span>

5. <span data-ttu-id="4b501-158">이 PowerShell 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-158">Run this PowerShell command:</span></span>

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

<span data-ttu-id="4b501-159">스크립트가 Permissions.csv라는 파일 하나를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-159">The script produces one file named Permissions.csv.</span></span> <span data-ttu-id="4b501-160">다음 단계를 수행하여 불법 응용 프로그램 권한 부여를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-160">Follow these steps to look for illicit application permission grants:</span></span>

1. <span data-ttu-id="4b501-161">ConsentType 열(G열)에서 값 "AllPrinciples"을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-161">In the ConsentType column (column G) search for the value "AllPrinciples".</span></span> <span data-ttu-id="4b501-162">AllPrincipals 사용 권한을 사용 하면 클라이언트 응용 프로그램에서 테 넌 시의 모든 사용자 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-162">The AllPrincipals permission allows the client application to access everyone's content in the tenancy.</span></span> <span data-ttu-id="4b501-163">기본 Office 365 응용 프로그램에서 제대로 작동하려면 이 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-163">Native Office 365 applications need this permission to work correctly.</span></span> <span data-ttu-id="4b501-164">이 권한을 가진 Microsoft가 아닌 모든 응용 프로그램은 신중하게 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-164">Every non-Microsoft application with this permission should be reviewed carefully.</span></span>

2. <span data-ttu-id="4b501-165">사용 권한 열(F열)에서 각 위임된 응용 프로그램에 대한 콘텐츠 사용 권한을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-165">In the Permission column (column F) review the permissions that each delegated application has to content.</span></span> <span data-ttu-id="4b501-166">"읽기" 및 "쓰기" 권한 또는 "\*.All" 권한을 찾아 적절하지 않을 수 있으므로 신중하게 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-166">Look for "Read" and "Write" permission or "\*.All" permission, and review these carefully because they may not be appropriate.</span></span>

3. <span data-ttu-id="4b501-167">동의가 부여된 특정 사용자를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-167">Review the specific users that have consents granted.</span></span> <span data-ttu-id="4b501-168">주목 받거나 영향력이 큰 사용자에게 부적절한 동의가 부여된 경우 추가 조사를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-168">If high profile or high impact users have inappropriate consents granted, you should investigate further.</span></span>

4. <span data-ttu-id="4b501-169">ClientDisplayName 열(C열)에서 의심스러운 앱을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-169">In the ClientDisplayName column (column C) look for apps that seem suspicious.</span></span> <span data-ttu-id="4b501-170">맞춤법이 잘못된 이름, 아주 밋밋한 이름 또는 해커 같은 이름을 사용 하는 앱은 신중하게 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-170">Apps with misspelled names, super bland names, or hacker-sounding names should be reviewed carefully.</span></span>

## <a name="determine-the-scope-of-the-attack"></a><span data-ttu-id="4b501-171">공격 범위 확인</span><span class="sxs-lookup"><span data-stu-id="4b501-171">Determine the scope of the attack</span></span>

<span data-ttu-id="4b501-172">응용 프로그램 액세스 인벤토리를 완료한 후에는 Office 365 **감사 로그**를 검토하여 침해의 전체 범위를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-172">After you have finished inventorying application access, review the Office 365 **audit log** to determine the full scope of the breach.</span></span> <span data-ttu-id="4b501-173">영향을 받는 사용자, 불법 응용 프로그램에서 조직에 액세스한 시간 프레임, 앱에 대한 사용 권한을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-173">Search on the affected users, the time frames that the illicit application had access to your organization, and the permissions the app had.</span></span> <span data-ttu-id="4b501-174">[Microsoft 365 보안 및 준수 센터](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)에서 **감사 로그**를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-174">You can search the **audit log** in the [Microsoft 365 Security and Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4b501-175">이 정보를 받으려면 공격 전에 [사서함 감사](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) 및 [관리자 및 사용자 활동에 대한 감사](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)가 설정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-175">[Mailbox auditing](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) and [Activity auditing for admins and users](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) must have been enabled prior to the attack for you to get this information.</span></span>

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a><span data-ttu-id="4b501-176">불법 동의 권한 부여를 방지하고 교정하는 방법</span><span class="sxs-lookup"><span data-stu-id="4b501-176">How to stop and remediate an illicit consent grant attack</span></span>

<span data-ttu-id="4b501-177">불법 사용 권한이 있는 응용 프로그램을 식별한 후 해당 액세스를 제거하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-177">After you have identified an application with illicit permissions, you have several ways to remove that access.</span></span>

- <span data-ttu-id="4b501-178">다음과 같은 방법으로 Azure Active Directory 포털에서 응용 프로그램의 사용 권한을 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-178">You can revoke the application's permission in the Azure Active Directory Portal by:</span></span>

  - <span data-ttu-id="4b501-179">**Azure Active Directory 사용자** 블레이드에서 영향을 받는 사용자로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-179">Navigate to the affected user in the **Azure Active Directory User** blade.</span></span>

  - <span data-ttu-id="4b501-180">**응용 프로그램**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-180">Select **Applications**.</span></span>

  - <span data-ttu-id="4b501-181">불법 응용 프로그램을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-181">Select the illicit application.</span></span>

  - <span data-ttu-id="4b501-182">드릴 다운에서 **제거**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-182">Click **Remove** in the drill down.</span></span>

- <span data-ttu-id="4b501-183">[Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)에 나와 있는 단계를 따라 PowerShell에서 OAuth 승인 부여를 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-183">You can revoke the OAuth consent grant with PowerShell by following the steps in [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).</span></span>

- <span data-ttu-id="4b501-184">[Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)의 단계에 따라 PowerShell을 사용하여 서비스 앱 역할 할당을 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-184">You can revoke the Service App Role Assignment with PowerShell by following the steps in [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).</span></span>

- <span data-ttu-id="4b501-185">영향을 받는 계정에 대한 로그인을 사용하지 않도록 설정할 수도 있습니다. 그러면 해당 계정의 데이터에 대한 앱 액세스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-185">You can also disable sign-in for the affected account altogether, which will in turn disable app access to data in that account.</span></span> <span data-ttu-id="4b501-186">이는 최종 사용자의 생산성에 이상적이지는 않지만 영향을 신속하게 제한려 한다면 단기적으로 조치가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-186">This isn't ideal for the end user's productivity, of course, but if you are working to limit impact quickly, it can be a viable short-term remediation.</span></span>

- <span data-ttu-id="4b501-187">테넌시에 통합 응용 프로그램을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-187">You can turn integrated applications off for your tenancy.</span></span> <span data-ttu-id="4b501-188">이는 최종 사용자가 테넌트 전반에 대한 동의를 부여하는 기능을 해제하는 극단적인 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-188">This is a drastic step that disables the ability for end users to grant consent on a tenant-wide basis.</span></span> <span data-ttu-id="4b501-189">따라서 사용자가 실수로 악성 응용 프로그램에 액세스를 부여하는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-189">This prevents your users from inadvertently granting access to a malicious application.</span></span> <span data-ttu-id="4b501-190">타사 응용 프로그램을 사용하여 생산성을 높일 수 있는 사용자 능력을 크게 손상시킬 수 있으므로 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-190">This isn't strongly recommended as it severely impairs your users' ability to be productive with third party applications.</span></span> <span data-ttu-id="4b501-191">[통합 앱을 설정하거나 해제](https://docs.microsoft.com/office365/admin/misc/integrated-apps)하는 단계를 수행하여 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-191">You can do this by following the steps in [Turning Integrated Apps on or off](https://docs.microsoft.com/office365/admin/misc/integrated-apps).</span></span>

## <a name="secure-office-365-like-a-cybersecurity-pro"></a><span data-ttu-id="4b501-192">사이버 보안 전문가와 같은 Office 365 보안</span><span class="sxs-lookup"><span data-stu-id="4b501-192">Secure Office 365 like a cybersecurity pro</span></span>

<span data-ttu-id="4b501-193">Office 365 구독에는 데이터 및 사용자를 보호하는 데 사용할 수있는 강력한 보안 기능이 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-193">Your Office 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="4b501-194">[Office 365 보안 로드맵: - 최초 30일, 90일 및 그 이후의 최우선 순위](security-roadmap.md)를 사용하여 Microsoft에서 권장하는 Office 365 테넌트 보안을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-194">Use the [Office 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Office 365 tenant.</span></span>

- <span data-ttu-id="4b501-195">처음 30일 이내에 수행 할 작업</span><span class="sxs-lookup"><span data-stu-id="4b501-195">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="4b501-196">이러한 작업들은 즉각적인 영향을 미치며 사용자에게 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-196">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="4b501-197">90일 이내에 수행해야 할 작업</span><span class="sxs-lookup"><span data-stu-id="4b501-197">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="4b501-198">이러한 작업들은 계획하고 구현하는 데 다소 시간이 걸리지만 보안 태세를 갖추는 데 큰 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-198">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="4b501-199">90일 초과</span><span class="sxs-lookup"><span data-stu-id="4b501-199">Beyond 90 days.</span></span> <span data-ttu-id="4b501-200">이러한 향상된 기능은 처음 90일간의 작업에서 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-200">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b501-201">참고 항목:</span><span class="sxs-lookup"><span data-stu-id="4b501-201">See also:</span></span>

- <span data-ttu-id="4b501-202">[내 응용 프로그램 목록에 예기치 않은 응용 프로그램](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application)은 데이터에 대한 액세스 권한이 있는 예기치 않은 응용 프로그램이 있다는 사실을 인식한 후 관리자가 수행할 수 있는 다양한 작업을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-202">[Unexpected application in my applications list](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) walks administrators through various actions they may want to take after realizing there are unexpected applications with access to data.</span></span>

- <span data-ttu-id="4b501-203">[Azure Active Directory와 응용 프로그램 통합](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent)은 동의 및 사용 권한에 대한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-203">[Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) is a high-level overview of consent and permissions.</span></span>

- <span data-ttu-id="4b501-204">[내 응용 프로그램 개발 문제](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map)는 다양한 동의 관련 문서의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-204">[Problems developing my application](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) provides links to various consent related articles.</span></span>

- <span data-ttu-id="4b501-205">[Azure AD(Active Directory)의 응용 프로그램 및 서비스 주체 개체](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects)는 응용 프로그램 모델의 핵심인 응용 프로그램 및 서비스 주체 개체에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-205">[Application and service principal objects in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.</span></span>

- <span data-ttu-id="4b501-206">[앱 액세스 관리](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps)는 관리자가 앱에 대한 사용자 액세스를 관리해야 하는 기능에 대한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="4b501-206">[Manage access to apps](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) is an overview of the capabilities that administrators have to manage user access to apps.</span></span>
