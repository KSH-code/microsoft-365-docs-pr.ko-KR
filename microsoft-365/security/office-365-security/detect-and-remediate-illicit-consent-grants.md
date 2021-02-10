---
title: 위조 동의 권한 부여 감지 및 수정
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: 365에서 무단 동의 권한 부여 공격을 인식하고 수정하는 Microsoft Office 방법을 배워보아야 합니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a1c724bb3b201e0ddf1edea4794606c7083605e8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165442"
---
# <a name="detect-and-remediate-illicit-consent-grants"></a><span data-ttu-id="b6fb0-103">위조 동의 권한 부여 감지 및 수정</span><span class="sxs-lookup"><span data-stu-id="b6fb0-103">Detect and Remediate Illicit Consent Grants</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b6fb0-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="b6fb0-104">**Applies to**</span></span>
- [<span data-ttu-id="b6fb0-105">Microsoft Defender for Office 365 요금제 1 및 계획 2</span><span class="sxs-lookup"><span data-stu-id="b6fb0-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="b6fb0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b6fb0-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="b6fb0-107">**요약** Office 365에서 불법 동의 권한 부여 공격을 인식하고 교정하는 방법에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-107">**Summary**  Learn how to recognize and remediate the illicit consent grants attack in Office 365.</span></span>

## <a name="what-is-the-illicit-consent-grant-attack-in-office-365"></a><span data-ttu-id="b6fb0-108">Office 365에서 불법 동의 권한 부여 공격은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="b6fb0-108">What is the illicit consent grant attack in Office 365?</span></span>

<span data-ttu-id="b6fb0-109">불법 동의 권한 부여 공격에는 공격자가 연락처 정보, 전자 메일 또는 문서 등의 데이터에 대한 액세스를 요청하는 Azure 등록 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-109">In an illicit consent grant attack, the attacker creates an Azure-registered application that requests access to data such as contact information, email, or documents.</span></span> <span data-ttu-id="b6fb0-110">그런 다음 공격자는 최종 사용자가 피싱 공격을 통해 또는 신뢰할 수있는 웹 사이트에 불법 코드를 주입하여 해당 응용 프로그램에 데이터 액세스 권한을 부여하도록 속임수를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-110">The attacker then tricks an end user into granting that application consent to access their data either through a phishing attack, or by injecting illicit code into a trusted website.</span></span> <span data-ttu-id="b6fb0-111">불법 응용 프로그램에 대한 동의가 부여되면 조직 계정이 없어도 데이터에 대한 계정 수준의 액세스 권한을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-111">After the illicit application has been granted consent, it has account-level access to data without the need for an organizational account.</span></span> <span data-ttu-id="b6fb0-112">침해된 계정에 대한 암호를 재설정하거나 계정에 MFA(다단계 인증)을 요구하는 등의 일반적인 조치 단계는 이러한 응용 프로그램이 타사 응용 프로그램이므로 조직 외부에 있기 때문에 이 유형의 공격에 효과적이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-112">Normal remediation steps, like resetting passwords for breached accounts or requiring Multi-Factor Authentication (MFA) on accounts, are not effective against this type of attack, since these are third-party applications and are external to the organization.</span></span>

<span data-ttu-id="b6fb0-113">이러한 공격은 정보를 호출하는 엔터티가 사용자가 아니라 자동화임을 가정하는 상호 작용 모델을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-113">These attacks leverage an interaction model which presumes the entity that is calling the information is automation and not a human.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6fb0-114">현재 앱에서의 부적격 동의 권한 부여에 문제가 있는 것으로 의심하나요?</span><span class="sxs-lookup"><span data-stu-id="b6fb0-114">Do you suspect you're experiencing problems with illicit consent-grants from an app, right now?</span></span> <span data-ttu-id="b6fb0-115">MCAS(Microsoft Cloud App Security)에는 OAuth 앱을 검색, 조사 및 수정하기 위한 도구가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-115">Microsoft Cloud App Security (MCAS) has tools to detect, investigate, and remediate your OAuth apps.</span></span> <span data-ttu-id="b6fb0-116">이 MCAS 문서에는 위험한 OAuth 앱을 조사하는 방법을 설명하는 [자습서가 있습니다.](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth)</span><span class="sxs-lookup"><span data-stu-id="b6fb0-116">This MCAS article has a tutorial that outlines how to go about [investigating risky OAuth apps](https://docs.microsoft.com/cloud-app-security/investigate-risky-oauth).</span></span> <span data-ttu-id="b6fb0-117">또한 사용자가 이러한 앱을 승인하는 앱 요청 권한을 조사하고 이러한 사용 권한 요청을 광범위하게 승인하거나 금지하도록 [OAuth](https://docs.microsoft.com/cloud-app-security/app-permission-policy) 앱 정책을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-117">You can also set [OAuth app policies](https://docs.microsoft.com/cloud-app-security/app-permission-policy) to investigate app-requested permissions, which users are authorizing these apps, and widely approve or ban these permissions requests.</span></span>

## <a name="what-does-an-illicit-consent-grant-attack-look-like-in-office-365"></a><span data-ttu-id="b6fb0-118">불법 동의 권한 부여는 Office 365에서 어떻게 보이나요?</span><span class="sxs-lookup"><span data-stu-id="b6fb0-118">What does an illicit consent grant attack look like in Office 365?</span></span>

<span data-ttu-id="b6fb0-119">감사 로그를 **검색하여** 이 공격의 IOC(손상 표시기)라고도 하는 기호를 찾아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-119">You need to search the **audit log** to find signs, also called Indicators of Compromise (IOC) of this attack.</span></span> <span data-ttu-id="b6fb0-120">여러 Azure 등록 응용 프로그램 및 대규모 사용자를 포함하는 조직의 경우 가장 좋은 방법은 주 단위로 조직 동의 권한 부여를 검토하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-120">For organizations with many Azure-registered applications and a large user base, the best practice is to review your organizations consent grants on a weekly basis.</span></span>

### <a name="steps-for-finding-signs-of-this-attack"></a><span data-ttu-id="b6fb0-121">이 공격의 신호를 찾는 단계</span><span class="sxs-lookup"><span data-stu-id="b6fb0-121">Steps for finding signs of this attack</span></span>

1. <span data-ttu-id="b6fb0-122">에서 **보안 & 규정 준수 센터를** 열 수 <https://protection.office.com> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-122">Open the **Security & Compliance Center** at <https://protection.office.com>.</span></span>

2. <span data-ttu-id="b6fb0-123">검색으로 **이동하여** 감사 로그 **검색을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6fb0-123">Navigate to **Search** and select **Audit log search**.</span></span>

3. <span data-ttu-id="b6fb0-124">검색(모든 활동 및 모든 사용자)을 검색하고 필요한 경우 시작 날짜와 종료 날짜를 입력한 다음 검색을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6fb0-124">Search (all activities and all users) and enter the start date and end date if required and then click **Search**.</span></span>

4. <span data-ttu-id="b6fb0-125">필터 **결과를 클릭하고** 작업 필드에 응용 프로그램에 대한 **동의를 입력합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6fb0-125">Click **Filter results** and enter Consent to application in the **Activity** field.</span></span>

5. <span data-ttu-id="b6fb0-126">결과를 클릭하여 활동의 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-126">Click on the result to see the details of the activity.</span></span> <span data-ttu-id="b6fb0-127">자세한 **정보를 클릭하여** 활동에 대한 세부 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-127">Click **More Information** to get details of the activity.</span></span> <span data-ttu-id="b6fb0-128">IsAdminContent가 True로 설정되어 있는지 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-128">Check to see if IsAdminContent is set to True.</span></span>

> [!NOTE]
>
> <span data-ttu-id="b6fb0-129">이벤트가 발생한 후 해당 감사 로그 항목이 검색 결과에 표시될 때 30분에서 24시간까지 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-129">It can take from 30 minutes up to 24 hours for the corresponding audit log entry to be displayed in the search results after an event occurs.</span></span>
>
> <span data-ttu-id="b6fb0-130">감사 기록을 보존하고 감사 로그에서 검색할 수 있는 시간은 Microsoft 365 구독, 특히 특정 사용자에게 할당된 라이선스 유형에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-130">The length of time that an audit record is retained and searchable in the audit log depends on your Microsoft 365 subscription, and specifically the type of the license that is assigned to a specific user.</span></span> <span data-ttu-id="b6fb0-131">자세한 내용은 [감사 로그](../../compliance/search-the-audit-log-in-security-and-compliance.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-131">For more information, see [Audit log](../../compliance/search-the-audit-log-in-security-and-compliance.md).</span></span>
>
> <span data-ttu-id="b6fb0-132">이 값이 true이면 전역 관리자 액세스 권한이 있는 사용자가 데이터에 대한 광범위한 액세스 권한을 부여할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-132">If this value is true, it indicates that someone with Global Administrator access may have granted broad access to data.</span></span> <span data-ttu-id="b6fb0-133">예기치 않은 상황이라면 [공격을 확인](#how-to-confirm-an-attack)하는 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-133">If this is unexpected, take steps to [confirm an attack](#how-to-confirm-an-attack).</span></span>

## <a name="how-to-confirm-an-attack"></a><span data-ttu-id="b6fb0-134">공격을 확인하는 방법</span><span class="sxs-lookup"><span data-stu-id="b6fb0-134">How to confirm an attack</span></span>

<span data-ttu-id="b6fb0-135">위에 나와 있는 IOCs의 인스턴스가 하나 이상 있는 경우 공격이 발생했음을 확실하게 확인하도록 추가 조사를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-135">If you have one or more instances of the IOCs listed above, you need to do further investigation to positively confirm that the attack occurred.</span></span> <span data-ttu-id="b6fb0-136">다음 세 가지 방법 중 한 가지를 사용하여 공격을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-136">You can use any of these three methods to confirm the attack:</span></span>

- <span data-ttu-id="b6fb0-137">Azure Active Directory 포털을 사용하는 인벤터리 응용 프로그램과 해당 사용 권한</span><span class="sxs-lookup"><span data-stu-id="b6fb0-137">Inventory applications and their permissions using the Azure Active Directory portal.</span></span> <span data-ttu-id="b6fb0-138">이 방법은 철저하지만 한번에 한 명의 사용자만 검사할 수 있어 검사할 사용자가 많은 경우에는 막대한 시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-138">This method is thorough, but you can only check one user at a time which can be very time consuming if you have many users to check.</span></span>

- <span data-ttu-id="b6fb0-139">PowerShell을 사용하는 인벤터리 응용 프로그램과 해당 사용 권한</span><span class="sxs-lookup"><span data-stu-id="b6fb0-139">Inventory applications and their permissions using PowerShell.</span></span> <span data-ttu-id="b6fb0-140">이 방법은 최소한의 오버 헤드를 사용하는 가장 빠르고 철저한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-140">This is the fastest and most thorough method, with the least amount of overhead.</span></span>

- <span data-ttu-id="b6fb0-141">사용자가 앱과 권한을 개별적으로 확인하고 조치를 위해 그 결과를 관리자에게 다시 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-141">Have your users individually check their apps and permissions and report the results back to the administrators for remediation.</span></span>

## <a name="inventory-apps-with-access-in-your-organization"></a><span data-ttu-id="b6fb0-142">조직에서 액세스 권한이 있는 인벤터리 앱</span><span class="sxs-lookup"><span data-stu-id="b6fb0-142">Inventory apps with access in your organization</span></span>

<span data-ttu-id="b6fb0-143">Azure Active Directory 포털이나 PowerShell을 사용하여 사용자를 위해 이 작업을 수행하거나 사용자가 응용 프로그램 액세스를 개별적으로 열거하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-143">You can do this for your users with either the Azure Active Directory Portal, or PowerShell or have your users individually enumerate their application access.</span></span>

### <a name="steps-for-using-the-azure-active-directory-portal"></a><span data-ttu-id="b6fb0-144">Azure Active Directory 포털 사용 단계</span><span class="sxs-lookup"><span data-stu-id="b6fb0-144">Steps for using the Azure Active Directory Portal</span></span>

<span data-ttu-id="b6fb0-145">[Azure Active Directory 포털](https://portal.azure.com/)를 사용하여 개별 사용자에게 사용 권한을 부여한 응용 프로그램을 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-145">You can look up the applications to which any individual user has granted permissions by using the [Azure Active Directory Portal](https://portal.azure.com/).</span></span>

1. <span data-ttu-id="b6fb0-146">관리 권한으로 Azure Portal에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-146">Sign in to the Azure Portal with administrative rights.</span></span>

2. <span data-ttu-id="b6fb0-147">Azure Active Directory 블레이드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-147">Select the Azure Active Directory blade.</span></span>

3. <span data-ttu-id="b6fb0-148">**사용자** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-148">Select **Users**.</span></span>

4. <span data-ttu-id="b6fb0-149">검토할 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-149">Select the user that you want to review.</span></span>

5. <span data-ttu-id="b6fb0-150">**응용 프로그램** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-150">Select **Applications**.</span></span>

<span data-ttu-id="b6fb0-151">사용자에게 할당된 앱과 응용 프로그램에 대한 사용 권한이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-151">This will show you the apps that are assigned to the user and what permissions the applications have.</span></span>

### <a name="steps-for-having-your-users-enumerate-their-application-access"></a><span data-ttu-id="b6fb0-152">사용자가 응용 프로그램에 액세스를 열거하도록 하는 단계</span><span class="sxs-lookup"><span data-stu-id="b6fb0-152">Steps for having your users enumerate their application access</span></span>

<span data-ttu-id="b6fb0-153">사용자가 https://myapps.microsoft.com(으)로 이동하여 해당 응용 프로그램에 대한 액세스를 검토할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-153">Have your users go to https://myapps.microsoft.com and review their own application access there.</span></span> <span data-ttu-id="b6fb0-154">액세스 권한이 있는 모든 앱을 확인하고, 세부 정보를 볼 수 있습니다(액세스 범위 포함). 또는 의심스러운 앱이나 불법 앱에 대한 사용 권한을 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-154">They should be able to see all the apps with access, view details about them (including the scope of access), and be able to revoke privileges to suspicious or illicit apps.</span></span>

### <a name="steps-for-doing-this-with-powershell"></a><span data-ttu-id="b6fb0-155">PowerShell로 이 작업을 수행하기 위한 단계</span><span class="sxs-lookup"><span data-stu-id="b6fb0-155">Steps for doing this with PowerShell</span></span>

<span data-ttu-id="b6fb0-156">불법 동의 권한 부여를 확인하는 가장 간단한 방법은 [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09)을 실행하는 것입니다. 이는 테넌시의 모든 사용자에 대한 모든 OAuth 동의 권한 부여 및 OAuth 앱을 하나의 .csv 파일로 덤프합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-156">The simplest way to verify the Illicit Consent Grant attack is to run [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09), which will dump all the OAuth consent grants and OAuth apps for all users in your tenancy into one .csv file.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="b6fb0-157">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b6fb0-157">Pre-requisites</span></span>

- <span data-ttu-id="b6fb0-158">Azure AD PowerShell 라이브러리가 설치됨</span><span class="sxs-lookup"><span data-stu-id="b6fb0-158">The Azure AD PowerShell library installed.</span></span>

- <span data-ttu-id="b6fb0-159">스크립트를 실행할 테넌트에 대한 전역 관리자 권한</span><span class="sxs-lookup"><span data-stu-id="b6fb0-159">Global administrator rights on the tenant that the script will be run against.</span></span>

- <span data-ttu-id="b6fb0-160">스크립트를 실행할 컴퓨터의 로컬 관리자</span><span class="sxs-lookup"><span data-stu-id="b6fb0-160">Local Administrator on the computer from which will run the scripts.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6fb0-161">관리 ***계정에*** 다단계 인증을 요구하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-161">We ***highly recommend*** that you require multi-factor authentication on your administrative account.</span></span> <span data-ttu-id="b6fb0-162">이 스크립트는 MFA 인증을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-162">This script supports MFA authentication.</span></span>

1. <span data-ttu-id="b6fb0-163">로컬 관리자 권한으로 스크립트를 실행할 컴퓨터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-163">Sign in to the computer that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="b6fb0-164">GitHub에서 [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) 스크립트를 실행할 폴더로 다운로드하거나 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-164">Download or copy the [Get-AzureADPSPermissions.ps1](https://gist.github.com/psignoret/41793f8c6211d2df5051d77ca3728c09) script from GitHub to a folder from which you will run the script.</span></span> <span data-ttu-id="b6fb0-165">이 폴더는 "permissions.csv" 출력 파일이 작성되는 폴더와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-165">This will be the same folder to which the output "permissions.csv" file will be written.</span></span>

3. <span data-ttu-id="b6fb0-166">PowerShell 인스턴스를 관리자로 열고 스크립트를 저장한 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-166">Open a PowerShell instance as an administrator and open to the folder you saved the script to.</span></span>

4. <span data-ttu-id="b6fb0-167">[Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread) cmdlet을 사용하여 디렉터리에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-167">Connect to your directory using the [Connect-AzureAD](https://docs.microsoft.com/powershell/module/azuread/connect-azuread) cmdlet.</span></span>

5. <span data-ttu-id="b6fb0-168">이 PowerShell 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-168">Run this PowerShell command:</span></span>

   ```powershell
   Get-AzureADPSPermissions.ps1 | Export-csv -Path "Permissions.csv" -NoTypeInformation
   ```

<span data-ttu-id="b6fb0-169">스크립트가 Permissions.csv라는 파일 하나를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-169">The script produces one file named Permissions.csv.</span></span> <span data-ttu-id="b6fb0-170">다음 단계를 수행하여 불법 응용 프로그램 권한 부여를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-170">Follow these steps to look for illicit application permission grants:</span></span>

1. <span data-ttu-id="b6fb0-171">ConsentType 열(G열)에서 값 "AllPrinciples"을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-171">In the ConsentType column (column G) search for the value "AllPrinciples".</span></span> <span data-ttu-id="b6fb0-172">AllPrincipals 권한을 사용하면 클라이언트 응용 프로그램이 테넌시의 모든 콘텐츠에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-172">The AllPrincipals permission allows the client application to access everyone's content in the tenancy.</span></span> <span data-ttu-id="b6fb0-173">기본 Microsoft 365 응용 프로그램이 제대로 작동하려면 이 사용 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-173">Native Microsoft 365 applications need this permission to work correctly.</span></span> <span data-ttu-id="b6fb0-174">이 권한을 가진 Microsoft가 아닌 모든 응용 프로그램은 신중하게 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-174">Every non-Microsoft application with this permission should be reviewed carefully.</span></span>

2. <span data-ttu-id="b6fb0-175">사용 권한 열(F열)에서 각 위임된 응용 프로그램에 대한 콘텐츠 사용 권한을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-175">In the Permission column (column F) review the permissions that each delegated application has to content.</span></span> <span data-ttu-id="b6fb0-176">"읽기" 및 "쓰기" 권한 또는 "\*.All" 권한을 찾아 적절하지 않을 수 있으므로 신중하게 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-176">Look for "Read" and "Write" permission or "\*.All" permission, and review these carefully because they may not be appropriate.</span></span>

3. <span data-ttu-id="b6fb0-177">동의가 부여된 특정 사용자를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-177">Review the specific users that have consents granted.</span></span> <span data-ttu-id="b6fb0-178">주목 받거나 영향력이 큰 사용자에게 부적절한 동의가 부여된 경우 추가 조사를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-178">If high profile or high impact users have inappropriate consents granted, you should investigate further.</span></span>

4. <span data-ttu-id="b6fb0-179">ClientDisplayName 열(C열)에서 의심스러운 앱을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-179">In the ClientDisplayName column (column C) look for apps that seem suspicious.</span></span> <span data-ttu-id="b6fb0-180">맞춤법이 잘못된 이름, 아주 밋밋한 이름 또는 해커 같은 이름을 사용 하는 앱은 신중하게 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-180">Apps with misspelled names, super bland names, or hacker-sounding names should be reviewed carefully.</span></span>

## <a name="determine-the-scope-of-the-attack"></a><span data-ttu-id="b6fb0-181">공격 범위 확인</span><span class="sxs-lookup"><span data-stu-id="b6fb0-181">Determine the scope of the attack</span></span>

<span data-ttu-id="b6fb0-182">응용 프로그램 액세스 인벤토리 작성을  완료한 후 감사 로그를 검토하여 위반의 전체 범위를 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-182">After you have finished inventorying application access, review the **audit log** to determine the full scope of the breach.</span></span> <span data-ttu-id="b6fb0-183">영향을 받는 사용자, 불법 응용 프로그램에서 조직에 액세스한 시간 프레임, 앱에 대한 사용 권한을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-183">Search on the affected users, the time frames that the illicit application had access to your organization, and the permissions the app had.</span></span> <span data-ttu-id="b6fb0-184">[Microsoft 365 보안 및 준수 센터](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)에서 **감사 로그** 를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-184">You can search the **audit log** in the [Microsoft 365 Security and Compliance Center](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b6fb0-185">이 정보를 받으려면 공격 전에 [사서함 감사](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) 및 [관리자 및 사용자 활동에 대한 감사](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)가 설정되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-185">[Mailbox auditing](https://docs.microsoft.com/microsoft-365/compliance/enable-mailbox-auditing) and [Activity auditing for admins and users](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) must have been enabled prior to the attack for you to get this information.</span></span>

## <a name="how-to-stop-and-remediate-an-illicit-consent-grant-attack"></a><span data-ttu-id="b6fb0-186">불법 동의 권한 부여를 방지하고 교정하는 방법</span><span class="sxs-lookup"><span data-stu-id="b6fb0-186">How to stop and remediate an illicit consent grant attack</span></span>

<span data-ttu-id="b6fb0-187">불법 사용 권한이 있는 응용 프로그램을 식별한 후 해당 액세스를 제거하는 방법에는 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-187">After you have identified an application with illicit permissions, you have several ways to remove that access.</span></span>

- <span data-ttu-id="b6fb0-188">다음과 같은 방법으로 Azure Active Directory 포털에서 응용 프로그램의 사용 권한을 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-188">You can revoke the application's permission in the Azure Active Directory Portal by:</span></span>

  - <span data-ttu-id="b6fb0-189">**Azure Active Directory 사용자** 블레이드에서 영향을 받는 사용자로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-189">Navigate to the affected user in the **Azure Active Directory User** blade.</span></span>

  - <span data-ttu-id="b6fb0-190">**응용 프로그램** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-190">Select **Applications**.</span></span>

  - <span data-ttu-id="b6fb0-191">불법 응용 프로그램을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-191">Select the illicit application.</span></span>

  - <span data-ttu-id="b6fb0-192">드릴 다운에서 **제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-192">Click **Remove** in the drill down.</span></span>

- <span data-ttu-id="b6fb0-193">[Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant)에 나와 있는 단계를 따라 PowerShell에서 OAuth 승인 부여를 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-193">You can revoke the OAuth consent grant with PowerShell by following the steps in [Remove-AzureADOAuth2PermissionGrant](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADOAuth2PermissionGrant).</span></span>

- <span data-ttu-id="b6fb0-194">[Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment)의 단계에 따라 PowerShell을 사용하여 서비스 앱 역할 할당을 해지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-194">You can revoke the Service App Role Assignment with PowerShell by following the steps in [Remove-AzureADServiceAppRoleAssignment](https://docs.microsoft.com/powershell/module/azuread/Remove-AzureADServiceAppRoleAssignment).</span></span>

- <span data-ttu-id="b6fb0-195">영향을 받는 계정에 대한 로그인을 사용하지 않도록 설정할 수도 있습니다. 그러면 해당 계정의 데이터에 대한 앱 액세스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-195">You can also disable sign-in for the affected account altogether, which will in turn disable app access to data in that account.</span></span> <span data-ttu-id="b6fb0-196">이는 최종 사용자의 생산성에 이상적이지는 않지만 영향을 신속하게 제한려 한다면 단기적으로 조치가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-196">This isn't ideal for the end user's productivity, of course, but if you are working to limit impact quickly, it can be a viable short-term remediation.</span></span>

- <span data-ttu-id="b6fb0-197">테넌시에 통합 응용 프로그램을 해제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-197">You can turn integrated applications off for your tenancy.</span></span> <span data-ttu-id="b6fb0-198">이는 최종 사용자가 테넌트 전반에 대한 동의를 부여하는 기능을 해제하는 극단적인 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-198">This is a drastic step that disables the ability for end users to grant consent on a tenant-wide basis.</span></span> <span data-ttu-id="b6fb0-199">따라서 사용자가 실수로 악성 응용 프로그램에 액세스를 부여하는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-199">This prevents your users from inadvertently granting access to a malicious application.</span></span> <span data-ttu-id="b6fb0-200">타사 응용 프로그램을 사용하여 생산성을 높일 수 있는 사용자 능력을 크게 손상시킬 수 있으므로 권장하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-200">This isn't strongly recommended as it severely impairs your users' ability to be productive with third party applications.</span></span> <span data-ttu-id="b6fb0-201">[통합 앱을 설정하거나 해제](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps)하는 단계를 수행하여 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-201">You can do this by following the steps in [Turning Integrated Apps on or off](https://docs.microsoft.com/microsoft-365/admin/misc/integrated-apps).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="b6fb0-202">사이버 보안 프로그램과 같은 Microsoft 365 보안</span><span class="sxs-lookup"><span data-stu-id="b6fb0-202">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="b6fb0-203">Microsoft 365 구독에는 데이터 및 사용자를 보호하는 데 사용할 수 있는 강력한 보안 기능이 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-203">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="b6fb0-204">[Microsoft 365 보안 로드맵 - 최초 30일, 90일 및 그 이후의 최우선 순위](security-roadmap.md)를 사용하여 Microsoft에서 권장하는 Microsoft 365 테넌트 보안을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-204">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="b6fb0-205">처음 30일 이내에 수행 할 작업</span><span class="sxs-lookup"><span data-stu-id="b6fb0-205">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="b6fb0-206">이러한 작업들은 즉각적인 영향을 미치며 사용자에게 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-206">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="b6fb0-207">90일 이내에 수행해야 할 작업</span><span class="sxs-lookup"><span data-stu-id="b6fb0-207">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="b6fb0-208">이러한 작업들은 계획하고 구현하는 데 다소 시간이 걸리지만 보안 태세를 갖추는 데 큰 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-208">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="b6fb0-209">90일 초과</span><span class="sxs-lookup"><span data-stu-id="b6fb0-209">Beyond 90 days.</span></span> <span data-ttu-id="b6fb0-210">이러한 향상된 기능은 처음 90일간의 작업에서 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-210">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6fb0-211">참고 항목:</span><span class="sxs-lookup"><span data-stu-id="b6fb0-211">See also:</span></span>

- <span data-ttu-id="b6fb0-212">[내 응용 프로그램 목록에 예기치 않은 응용 프로그램](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application)은 데이터에 대한 액세스 권한이 있는 예기치 않은 응용 프로그램이 있다는 사실을 인식한 후 관리자가 수행할 수 있는 다양한 작업을 안내합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-212">[Unexpected application in my applications list](https://docs.microsoft.com/azure/active-directory/application-access-unexpected-application) walks administrators through various actions they may want to take after realizing there are unexpected applications with access to data.</span></span>

- <span data-ttu-id="b6fb0-213">[Azure Active Directory와 응용 프로그램 통합](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent)은 동의 및 사용 권한에 대한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-213">[Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-apps-permissions-consent) is a high-level overview of consent and permissions.</span></span>

- <span data-ttu-id="b6fb0-214">[내 응용 프로그램 개발 문제](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map)는 다양한 동의 관련 문서의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-214">[Problems developing my application](https://docs.microsoft.com/azure/active-directory/active-directory-application-dev-development-content-map) provides links to various consent related articles.</span></span>

- <span data-ttu-id="b6fb0-215">[Azure AD(Active Directory)의 응용 프로그램 및 서비스 주체 개체](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects)는 응용 프로그램 모델의 핵심인 응용 프로그램 및 서비스 주체 개체에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-215">[Application and service principal objects in Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-application-objects) provides an overview of the Application and Service principal objects that are core to the application model.</span></span>

- <span data-ttu-id="b6fb0-216">[앱 액세스 관리](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps)는 관리자가 앱에 대한 사용자 액세스를 관리해야 하는 기능에 대한 개요입니다.</span><span class="sxs-lookup"><span data-stu-id="b6fb0-216">[Manage access to apps](https://docs.microsoft.com/azure/active-directory/active-directory-managing-access-to-apps) is an overview of the capabilities that administrators have to manage user access to apps.</span></span>
