<span data-ttu-id="88161-101">ID 인프라 관련 추가 권장 사항에 대해서는 [필수 구성 요소](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88161-101">Also see [Prerequisites](https://docs.microsoft.com/microsoft-365-enterprise/identity-access-policies#prerequisites) for additional recommendations on identity infrastructure.</span></span>

<a name="crit-identity-global-admin"></a>
### <a name="required-your-global-administrator-accounts-are-protected"></a><span data-ttu-id="88161-102">필수: 전역 관리자 계정 보호</span><span class="sxs-lookup"><span data-stu-id="88161-102">Required: Your global administrator accounts are protected</span></span> 

<span data-ttu-id="88161-103">Microsoft 365 구독을 위반할 수 있는 공격자의 자격 증명 손상을 방지하기 위해 [Office 365 전역 관리자 계정을 보호](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-103">You've [protected your Office 365 global administrator accounts](https://docs.microsoft.com/office365/enterprise/protect-your-global-administrator-accounts) to thwart  credential compromise by attackers that can lead to breaches of your Microsoft 365 subscription.</span></span>

<span data-ttu-id="88161-104">이 요구 사항을 건너뛰면 전역 관리자 계정이 공격 받고 손상되기 쉽기 때문에 공격자가 시스템 전체 액세스 권한을 얻어 데이터를 수집 또는 삭제하거나 금품을 요구하기 위해 보유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-104">If you skip this requirement, your global administrator accounts can be susceptible to attack and compromise, allowing an attacker to gain system-wide access to your data for harvesting, destruction, or ransom.</span></span>

<span data-ttu-id="88161-105">필요한 경우 [1단계](../identity-create-protect-global-admins.md#identity-global-admin)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-105">If needed, [Step 1](../identity-create-protect-global-admins.md#identity-global-admin) can help you meet this requirement.</span></span>

#### <a name="how-to-test"></a><span data-ttu-id="88161-106">테스트하는 방법</span><span class="sxs-lookup"><span data-stu-id="88161-106">How to test</span></span>

<span data-ttu-id="88161-107">다음 단계를 사용하여 전역 관리자 계정을 보호했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-107">Use these steps to verify that you've protected your global administrator accounts:</span></span>

1. <span data-ttu-id="88161-108">PowerShell 명령 프롬프트에서 다음의 Azure Active Directory PowerShell for Graph 명령을 실행하세요.</span><span class="sxs-lookup"><span data-stu-id="88161-108">Run the following Azure Active Directory PowerShell for Graph command at the PowerShell command prompt.</span></span> <span data-ttu-id="88161-109">전담 전역 관리자 계정 목록만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="88161-109">You should see only the list of dedicated global administrator accounts.</span></span>
   ```
   Get-AzureADDirectoryRole | where { $_.DisplayName -eq "Company Administrator" } | Get-AzureADDirectoryRoleMember | Ft DisplayName
   ```
2. <span data-ttu-id="88161-110">1단계의 각 계정을 사용하여 Office 365에 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-110">Sign in to Office 365 using each of the accounts from step 1.</span></span> <span data-ttu-id="88161-111">로그인할 때마다 Azure 다단계 인증 및 조직에서 사용 가능한 가장 강력한 형태의 보조 인증을 요구해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-111">Each sign in must require Azure Multi-Factor Authentication and the strongest form of secondary authentication available in your organization.</span></span>

> [!Note]
> <span data-ttu-id="88161-112">그래프 모듈용 Azure Active Directory PowerShell 설치 및 Office 365 로그인에 대한 지침은 [Office 365 PowerShell에 연결](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88161-112">See [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell) for instructions on installing the Azure Active Directory PowerShell for Graph module and signing in to Office 365.</span></span>

<a name="crit-identity-pim"></a>
### <a name="optional-you-have-set-up-privileged-identity-management-to-support-on-demand-assignment-of-the-global-administrator-role"></a><span data-ttu-id="88161-113">선택: 요청 시 전역 관리자 역할을 할당할 수 있도록 Privileged Identity Management 설정</span><span class="sxs-lookup"><span data-stu-id="88161-113">Optional: You have set up Privileged Identity Management to support on-demand assignment of the global administrator role</span></span>

<span data-ttu-id="88161-114">[Azure AD PIM(Privileged Identity Management) 구성](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)의 지침을 사용하여 Azure AD 테넌트에서 PIM을 사용하도록 설정하고 전역 관리자 계정을 적격 관리자로 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-114">You've used the instructions in [Configure Azure AD Privileged Identity Management (PIM)](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure) to enable PIM in your Azure AD tenant and configured your global administrator accounts as eligible admins.</span></span>

<span data-ttu-id="88161-115">또한 [Azure AD에서 하이브리드 및 클라우드 배포에 대한 권한 있는 액세스 보호](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)의 권장 사항을 사용하여 권한 있는 액세스를 사이버 공격자로부터 보호하는 로드맵을 마련해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-115">You've also used the recommendations in [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices) to develop a roadmap that secures privileged access against cyber attackers.</span></span>

<span data-ttu-id="88161-116">이 옵션을 건너뛰면 전역 관리자 계정이 지속적인 온라인 공격을 받을 수 있으며, 손상된 경우 공격자가 중요한 정보를 수집 또는 삭제하거나 금품을 요구하기 위해 보유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-116">If you skip this option, your global administrator accounts are subject to ongoing online attack and, if compromised, can allow an attacker to harvest, destroy, or hold your sensitive information for ransom.</span></span>

<span data-ttu-id="88161-117">필요한 경우 [1단계](../identity-create-protect-global-admins.md#identity-pim)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-117">If needed, [Step 1](../identity-create-protect-global-admins.md#identity-pim) can help you with this option.</span></span>

<a name="crit-identity-pam"></a>
### <a name="optional-you-have-configure-privileged-access-management-in-office-365"></a><span data-ttu-id="88161-118">선택 사항: Office 365에 권한이 부여된 액세스 관리를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-118">Optional: You have configure privileged access management in Office 365</span></span>

<span data-ttu-id="88161-119">권한이 부여된 액세스를 사용하고 조직에서 하나 이상의 권한이 부여된 액세스 정책을 만들어내기 위해 [Office 365에서 권한이 부여된 액세스 관리 구성](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration)의 정보를 사용하였습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-119">You've used the information in the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic to enable privileged access and create one or more privileged access policies in your organization.</span></span> <span data-ttu-id="88161-120">이러한 정책을 구성하고 중요한 데이터에 대한 액세스 또는 중요한 구성 설정에 대한 액세스를 위해 적기에 맞는 액세스가 활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="88161-120">You've configured these policies and just-in-time access is enabled for access to sensitive data or access to critical configuration settings.</span></span>

<span data-ttu-id="88161-121">필요한 경우 [1단계](../identity-create-protect-global-admins.md#identity-pam)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-121">If needed, [Step 1](../identity-create-protect-global-admins.md#identity-pam) can help you meet this requirement.</span></span> 

<a name="crit-password-prot"></a>
### <a name="optional-azure-ad-password-protection-is-banning-the-use-of-weak-passwords"></a><span data-ttu-id="88161-122">선택 사항: Azure AD 암호 보호를 사용하면 취약한 암호의 사용을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-122">Optional: Azure AD password protection is banning the use of weak passwords</span></span>

<span data-ttu-id="88161-123">전역적으로 금지된 암호 및 선택적으로 사용자 지정 약관에 대해 [클라우드](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) 및 [온-프레미스 AD DS(Active Directory Domain Services)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises)에서 잘못된 암호 금지를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-123">You have enabled the banning of bad passwords [in the cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) and for your [on-premises Active Directory Domain Services (AD DS)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises) for global banned passwords and, optionally, for custom terms.</span></span>

<span data-ttu-id="88161-124">필요한 경우 [2단계](../identity-secure-your-passwords.md#identity-password-prot)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-124">If needed, [Step 2](../identity-secure-your-passwords.md#identity-password-prot) can help you with this option.</span></span>

<a name="crit-identity-pw-reset"></a>
### <a name="optional-users-can-reset-their-own-passwords"></a><span data-ttu-id="88161-125">선택: 사용자가 자신의 암호를 재설정할 수 있음</span><span class="sxs-lookup"><span data-stu-id="88161-125">Optional: Users can reset their own passwords</span></span>

<span data-ttu-id="88161-126">[Azure AD 셀프 서비스 암호 재설정 신속 배포](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)를 사용하여 사용자에 대해 암호 재설정을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-126">You've used [Azure AD self-service password reset rapid deployment](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to configure password reset for your users.</span></span>

<span data-ttu-id="88161-127">이 조건을 충족하지 않으면 사용자가 계정 관리자에게 암호 재설정을 요청해야 하므로 추가 IT 관리 오버헤드가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-127">If you don’t meet this condition, users will be dependent on user account administrators to reset their passwords, resulting in additional IT administration overhead.</span></span>

<span data-ttu-id="88161-128">필요한 경우 [2단계](../identity-secure-your-passwords.md#identity-pw-reset)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-128">If needed, [Step 2](../identity-secure-your-passwords.md#identity-pw-reset) can help you with this option.</span></span>

<a name="crit-identity-sso"></a>
### <a name="optional-users-can-sign-in-using-azure-ad-seamless-single-sign-on"></a><span data-ttu-id="88161-129">선택: 사용자가 Azure AD Seamless Single Sign-On을 사용하여 로그인할 수 있음</span><span class="sxs-lookup"><span data-stu-id="88161-129">Optional: Users can sign in using Azure AD Seamless Single Sign-on</span></span>

<span data-ttu-id="88161-130">조직에서 [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)을 사용하도록 설정하여 사용자가 Office 365와 같은 클라우드 기반 응용 프로그램에 로그인하는 방법을 간소화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-130">You enabled [Azure AD Connect: Seamless Single Sign-On](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start) for your organization to simplify how users sign in to cloud-based applications, such as Office 365.</span></span>

<span data-ttu-id="88161-131">이 옵션을 건너뛰면 사용자가 Azure AD 테넌트를 사용하는 추가 응용 프로그램에 액세스할 때 자격 증명을 제공하라는 메시지가 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-131">If you skip this option, your users might be prompted to provide credentials when they access additional applications that use you Azure AD tenant.</span></span>

<span data-ttu-id="88161-132">필요한 경우 [2단계](../identity-secure-your-passwords.md#identity-sso)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-132">If needed, [Step 2](../identity-secure-your-passwords.md#identity-sso) can help you with this option.</span></span>

<a name="crit-identity-custom-sign-in"></a>
### <a name="optional-the-office-365-sign-in-screen-is-personalized-for-your-organization"></a><span data-ttu-id="88161-133">선택: Office 365 로그인 화면을 조직에 맞게 개인 설</span><span class="sxs-lookup"><span data-stu-id="88161-133">Optional: The Office 365 sign-in screen is personalized for your organization</span></span>

<span data-ttu-id="88161-134">[로그인 및 액세스 패널 페이지에 회사 브랜딩을 추가](https://aka.ms/aadpaddbranding)하여 Office 365 로그인 페이지를 조직의 브랜딩을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-134">You have used [Add company branding to your sign-in and Access Panel pages](https://aka.ms/aadpaddbranding) to add your organization’s branding to the Office 365 sign-in page.</span></span>

<span data-ttu-id="88161-135">이 옵션을 건너뛰면 사용자에게 일반 Office 365 로그인 화면이 표시되므로 조직의 사이트에 로그인 중인지 확신하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-135">If you skip this option, your users will see a generic Office 365 sign-in screen and might not be confident that they’re signing into your organization’s site.</span></span>

<span data-ttu-id="88161-136">필요한 경우 [2단계](../identity-secure-your-passwords.md#identity-custom-sign-in)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-136">If needed, [Step 2](../identity-secure-your-passwords.md#identity-custom-sign-in) can help you with this option.</span></span>


<a name="crit-identity-mfa"></a>
### <a name="optional-azure-multi-factor-authentication-is-enabled-for-your-users"></a><span data-ttu-id="88161-137">선택 사항: 사용자에 대해 Azure 다단계 인증 사용</span><span class="sxs-lookup"><span data-stu-id="88161-137">Optional: Azure Multi-Factor Authentication is enabled for your users</span></span>

<span data-ttu-id="88161-138">[Azure 다단계 인증 계획](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) 및 [조건부 액세스 정책](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access)을 사용하여 사용자 계정에 대해 Azure MFA(Multi-Factor Authentication)를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-138">You used [Plan for Azure Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted) and [Conditional Access policies](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-getstarted#enable-multi-factor-authentication-with-conditional-access) to enable Azure Multi-Factor Authentication (MFA) for your user accounts.</span></span>

<span data-ttu-id="88161-p104">이 옵션을 건너뛰면 사용자 계정이 사이버 공격자에 의한 자격 증명 손상에 취약해집니다. 사용자 계정의 암호가 손상되면 관리자 역할과 같은 계정의 모든 리소스 및 기능을 공격자가 사용할 수 있습니다. 따라서 공격자가 내부 문서 및 기타 데이터를 복사 또는 삭제하거나 금품을 요구하기 위해 보유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-p104">If you skip this option, your user accounts are vulnerable to credential compromise by cyber attackers. If a user account’s password is compromised, all the resources and capabilities of the account, such as administrator roles, are available to the attacker. This allows the attacker to copy, destroy, or hold for ransom internal documents and other data.</span></span>

<span data-ttu-id="88161-142">필요한 경우 [3단계](../identity-secure-user-sign-ins.md#identity-mfa)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-142">If needed, [Step 3](../identity-secure-user-sign-ins.md#identity-mfa) can help you with this option.</span></span>

#### <a name="how-to-test"></a><span data-ttu-id="88161-143">테스트하는 방법</span><span class="sxs-lookup"><span data-stu-id="88161-143">How to test</span></span>

1.  <span data-ttu-id="88161-144">테스트 사용자 계정을 만들고 이 계정에 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-144">Create a test user account and assign them a license.</span></span> 
2.  <span data-ttu-id="88161-145">휴대폰에 문자 메시지를 보내는 등 실제 사용자 계정에 사용 중인 추가 인증 방법으로 테스트 사용자 계정에 대해 Azure 다단계 인증을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-145">Configure Azure Multi-Factor Authentication for the test user account with the additional verification method that you are using for actual user accounts, such as sending a text message to your phone.</span></span> 
3.  <span data-ttu-id="88161-146">테스트 사용자 계정을 사용하여 Office 365 포털에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-146">Sign in to the Office 36 portal with the test user account.</span></span>
4.  <span data-ttu-id="88161-147">MFA에서 추가 인증 정보를 묻고 인증에 성공하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-147">Verify that MFA prompts you for the additional verification information and results in a successful authentication.</span></span> 
5.  <span data-ttu-id="88161-148">테스트 사용자 계정을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-148">Delete the test user account.</span></span>

<a name="crit-identity-ident-prot"></a>
### <a name="optional-azure-ad-identity-protection-is-enabled-to-protect-against-credential-compromise-microsoft-365-enterprise-e5-only"></a><span data-ttu-id="88161-149">선택: Azure AD ID 보호를 사용하도록 설정하여 자격 증명 손상으로부터 보호(Microsoft 365 Enterprise E5만 해당)</span><span class="sxs-lookup"><span data-stu-id="88161-149">Optional: Azure AD Identity Protection is enabled to protect against credential compromise (Microsoft 365 Enterprise E5 only)</span></span>

<span data-ttu-id="88161-150">다음을 위해 Azure AD ID 보호를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-150">You've enabled Azure AD Identity Protection to:</span></span>

- <span data-ttu-id="88161-151">잠재적인 ID 취약점 해결</span><span class="sxs-lookup"><span data-stu-id="88161-151">Address potential identity vulnerabilities.</span></span>
- <span data-ttu-id="88161-152">가능한 자격 증명 손상 시도 감지</span><span class="sxs-lookup"><span data-stu-id="88161-152">Detect possible credential compromise attempts.</span></span>
- <span data-ttu-id="88161-153">지속적인 의심스러운 ID 사건 조사 및 해결</span><span class="sxs-lookup"><span data-stu-id="88161-153">Investigate and address ongoing suspicious identity incidents.</span></span>

<span data-ttu-id="88161-p105">이 옵션을 건너뛰면 자격 증명 손상 시도를 감지하거나 자동으로 차단할 수 없으며 ID 관련 보안 사건을 조사할 수 없습니다. 이 경우 잠재적으로 조직이 성공적인 자격 증명 손상에 취약해져 조직의 중요한 데이터가 위협에 노출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-p105">If you skip this option, you won’t be able to detect or automatically thwart credential compromise attempts or investigate identity-related security incidents. This potentially leaves your organization vulnerable to a successful credential compromise and the resulting threat to your organization’s sensitive data.</span></span>

<span data-ttu-id="88161-156">필요한 경우 [3단계](../identity-secure-user-sign-ins.md#identity-ident-prot)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-156">If needed, [Step 3](../identity-secure-user-sign-ins.md#identity-ident-prot) can help you with this option.</span></span>


#### <a name="how-to-test"></a><span data-ttu-id="88161-157">테스트하는 방법</span><span class="sxs-lookup"><span data-stu-id="88161-157">How to test</span></span>

1. <span data-ttu-id="88161-158">초기 암호를 사용하여 테스트 사용자 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="88161-158">Create a test user account with an initial password.</span></span>
2. <span data-ttu-id="88161-159">[사용자가 Office 365에서 암호를 직접 다시 설정하도록 허용](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) 단계를 사용하여 테스트 사용자 계정의 암호를 다시 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-159">Use the steps in [Let users reset their own passwords in Office 365](https://docs.microsoft.com/office365/admin/add-users/let-users-reset-passwords) to reset the password on the test user account.</span></span>
3. <span data-ttu-id="88161-160">로그아웃했다가 재설정 암호를 사용하여 테스트 사용자 계정에 다시 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-160">Sign out and then sign in to the test user account using the reset password.</span></span>
4. <span data-ttu-id="88161-161">테스트 사용자 계정을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-161">Delete the test user account.</span></span>

<a name="crit-identity-sync"></a>
### <a name="required-for-hybrid-identity-users-and-groups-are-synchronized-with-azure-ad"></a><span data-ttu-id="88161-162">하이브리드 ID에 필수: 사용자 및 그룹을 Azure AD와 동기화</span><span class="sxs-lookup"><span data-stu-id="88161-162">Required for hybrid identity: Users and groups are synchronized with Azure AD</span></span>

<span data-ttu-id="88161-163">기존 온-프레미스 AD DS(Active Directory Domain Services)가 있는 경우 Azure AD Connect를 사용하여 온-프레미스 AD DS의 사용자 계정 및 그룹을 Azure AD 테넌트에 동기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-163">If you have an existing on-premises Active Directory Domain Services (AD DS), you have used Azure AD Connect to synchronize user accounts and groups from your on-premises AD DS to your Azure AD tenant.</span></span>

<span data-ttu-id="88161-164">디렉터리 동기화를 사용하는 경우 사용자는 자신의 컴퓨터에 로그인하고 온-프레미스 리소스에 액세스하는 데 사용하는 것과 동일한 자격 증명을 통해 Office 365 및 다른 Microsoft 클라우드 서비스에 로그인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-164">With directory synchronization, your users can sign in to Office 365 and other Microsoft cloud services using the same credentials that they use to sign in to their computers and access on-premises resources.</span></span>

<span data-ttu-id="88161-165">필요한 경우, [4단계](../identity-add-user-accounts.md#identity-sync)를 통해 이 요구 사항을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-165">If needed, [Step 4](../identity-add-user-accounts.md#identity-sync) can help you meet this requirement.</span></span>

<span data-ttu-id="88161-166">이 요구 사항을 건너뛰면 다음 두 가지 사용자 계정 및 그룹 집합을 가지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88161-166">If you skip this requirement, you’ll have two sets of user accounts and groups:</span></span>

- <span data-ttu-id="88161-167">온-프레미스 AD DS에 속해 있는 사용자 계정 및 그룹</span><span class="sxs-lookup"><span data-stu-id="88161-167">User accounts and groups that exist in your on-premises AD DS</span></span>
- <span data-ttu-id="88161-168">Azure AD 테넌트에 속해 있는 사용자 계정 및 그룹</span><span class="sxs-lookup"><span data-stu-id="88161-168">User accounts and groups that exist in your Azure AD tenant</span></span>

<span data-ttu-id="88161-p106">이 상태에서는 IT 관리자 및 사용자가 두 가지 사용자 계정 및 그룹 집합을 수동으로 유지 관리해야 합니다. 이 경우 계정, 암호 및 그룹이 동기화되지 않는 상황이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-p106">In this state, the two sets of user accounts and groups must be manually maintained by both IT administrators and users. This will inevitably lead to unsynchronized accounts, their passwords, and groups.</span></span>

#### <a name="how-to-test"></a><span data-ttu-id="88161-171">테스트 방법</span><span class="sxs-lookup"><span data-stu-id="88161-171">How to test</span></span>
<span data-ttu-id="88161-172">온-프레미스 자격 증명과의 동기화가 올바르게 작동하는지 확인하려면 온-프레미스 자격 증명을 사용하여 Office 포털에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-172">To verify that authentication with on-premises credentials works correctly, sign in to the Office portal with your on-premises credentials.</span></span>

<span data-ttu-id="88161-173">디렉터리 동기화가 올바르게 작동하는지 확인하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-173">To verify that directory synchronization is working correctly, do the following:</span></span>

1.  <span data-ttu-id="88161-174">AD DS에서 새 테스트 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="88161-174">Create a new test group in AD DS.</span></span>
2.  <span data-ttu-id="88161-175">동기화 시간까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="88161-175">Wait for the synchronization time.</span></span>
3.  <span data-ttu-id="88161-176">Azure AD 테넌트를 확인하여 새 테스트 그룹 이름이 표시되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-176">Check your Azure AD tenant to verify that the new test group name appears.</span></span>

<a name="crit-identity-sync-health"></a>
### <a name="optional-directory-synchronization-is-monitored"></a><span data-ttu-id="88161-177">선택: 디렉터리 동기화 모니터링</span><span class="sxs-lookup"><span data-stu-id="88161-177">Optional: Directory synchronization is monitored</span></span>

<span data-ttu-id="88161-178">[동기화에 Azure AD Connect Health를 사용](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync)(암호 동기화용)하거나 [AD FS에서 Azure AD Connect Health를 사용](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs)(페더레이션된 인증용)하고 Azure AD Connect Health를 배포해야 합니다. 여기에는 다음이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="88161-178">You've used [Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) (for password synchronization) or [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) (for federated authentication) and have deployed Azure AD Connect Health, which involves:</span></span>

- <span data-ttu-id="88161-179">각 온-프레미스 ID 서버에 Azure AD Connect Health 에이전트를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-179">Installing the Azure AD Connect Health agent on each of your on-premises identity servers.</span></span>
- <span data-ttu-id="88161-180">Azure AD Connect Health 포털을 사용하여 진행 중인 동기화의 상태를 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-180">Using the Azure AD Connect Health portal to monitor the state of the ongoing synchronization.</span></span>

<span data-ttu-id="88161-181">이 옵션을 건너뛰면 클라우드 기반 ID 인프라의 상태를 보다 정확하게 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-181">If you skip this option, you can more accurately assess the state of your cloud-based identity infrastructure.</span></span>

<span data-ttu-id="88161-182">필요한 경우 [4단계](../identity-add-user-accounts.md#identity-sync-health)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-182">If needed, [Step 4](../identity-add-user-accounts.md#identity-sync-health) can help you with this option.</span></span>

#### <a name="how-to-test"></a><span data-ttu-id="88161-183">테스트하는 방법</span><span class="sxs-lookup"><span data-stu-id="88161-183">How to test</span></span>
<span data-ttu-id="88161-184">Azure AD Connect Health 포털에는 온-프레미스 도메인 컨트롤러와 진행 중인 동기화의 현재 및 올바른 상태가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="88161-184">The Azure AD Connect Health portal shows the current and correct state of your on-premises domain controllers and the ongoing synchronization.</span></span>


<a name="crit-identity-pw-writeback"></a>
### <a name="optional-password-writeback-is-enabled-for-your-users"></a><span data-ttu-id="88161-185">선택: 사용자에 대해 암호 쓰기 저장 사용</span><span class="sxs-lookup"><span data-stu-id="88161-185">Optional: Password writeback is enabled for your users</span></span>

<span data-ttu-id="88161-186">[암호 쓰기 저장을 지원하는 Azure AD SSPR](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started)의 지침을 사용하여 Microsoft 365 Enterprise 구독의 Azure AD 테넌트에 대해 암호 쓰기 저장을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-186">You've used the instructions in [Azure AD SSPR with password writeback](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-getting-started) to enable password writeback for the Azure AD tenant of your Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="88161-187">이 옵션을 건너뛰면 온-프레미스 네트워크에 연결되지 않은 사용자가 IT 관리자를 통해 AD DS 암호를 다시 설정하거나 잠금을 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-187">If you skip this option, users who aren’t connected to your on-premises network must reset or unlock their AD DS passwords through an IT administrator.</span></span>

<span data-ttu-id="88161-188">필요한 경우 [4단계](../identity-add-user-accounts.md#identity-pw-writeback)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-188">If needed, [Step 4](../identity-add-user-accounts.md#identity-pw-writeback) can help you with this option.</span></span>

>[!Note]
><span data-ttu-id="88161-189">암호 쓰기 저장은 Azure AD에서 계정 손상의 높은 위험을 감지한 경우 사용자에게 온-프레미스 암호를 변경하도록 요구하는 등 Azure AD ID 보호 기능을 최대한 활용하기 위해 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-189">Password writeback is required to fully utilize Azure AD Identity Protection features, such as requiring users to change their on-premises passwords when Azure AD has detected a high risk of account compromise.</span></span>
>

#### <a name="how-to-test"></a><span data-ttu-id="88161-190">테스트하는 방법</span><span class="sxs-lookup"><span data-stu-id="88161-190">How to test</span></span>

<span data-ttu-id="88161-191">Office 365에서 암호를 변경하여 암호 쓰기 저장을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-191">You test password writeback by changing your password in Office 365.</span></span> <span data-ttu-id="88161-192">계정 및 새 암호를 사용하여 온-프레미스 AD DS 리소스에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-192">You should be able to use your account and new password to access on-premises AD DS resources.</span></span>

1. <span data-ttu-id="88161-193">온-프레미스 AD DS에서 테스트 사용자 계정을 만들고 디렉터리 동기화가 발생하도록 허용한 다음 Office 365 관리 센터에서 Microsoft 365 Enterprise 라이선스를 부여합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-193">Create a test user account in your on-premises AD DS, allow directory synchronization to occur, and then grant it a Microsoft 365 Enterprise license in the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="88161-194">온-프레미스 AD DS 도메인에 가입된 원격 컴퓨터에서 테스트 사용자 계정의 자격 증명을 사용하여 컴퓨터 및 Office 포털에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-194">From a remote computer that is joined to your on-premises AD DS domain, sign in to the computer and the Office portal using the credentials of the test user account.</span></span>
3. <span data-ttu-id="88161-195">**설정 > Office 365 설정 > 암호 > 암호 변경**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-195">Select **Settings > Office 365 settings > Password > Change password**.</span></span>
4. <span data-ttu-id="88161-196">현재 암호와 새 암호를 차례로 입력하고 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-196">Type the current password, type a new password, and then confirm it.</span></span>
5. <span data-ttu-id="88161-197">Office 포털과 원격 컴퓨터에서 로그아웃한 다음 테스트 사용자 계정과 새 암호를 사용하여 컴퓨터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-197">Sign out of the Office portal and the remote computer and then sign in to the computer using the test user account and its new password.</span></span> <span data-ttu-id="88161-198">이는 Azure AD 테넌트를 사용하여 온-프레미스 AD DS 사용자 계정의 암호를 변경할 수 있음을 입증합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-198">This proves that you were able to change the password of an on-premises AD DS user account using the Azure AD tenant.</span></span>

#### <a name="how-to-test"></a><span data-ttu-id="88161-199">테스트하는 방법</span><span class="sxs-lookup"><span data-stu-id="88161-199">How to test</span></span>

<span data-ttu-id="88161-200">사용자 계정 이름과 Azure 다단계 인증을 사용하 여 Office 365 포털에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-200">Sign in to the Office 365 portal with your user account name and Azure Multi-Factor Authentication.</span></span> <span data-ttu-id="88161-201">로그인 페이지에서 사용자 지정 브랜드 요소를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-201">You should see your custom branding elements on the sign-in page.</span></span>


<a name="crit-identity-self-service-groups"></a>
### <a name="optional-self-service-group-management-is-enabled-for-specific-azure-ad-security-and-office-365-groups"></a><span data-ttu-id="88161-202">선택: 특정 Azure AD 보안 및 Office 365 그룹에 대해 셀프 서비스 관리 사용</span><span class="sxs-lookup"><span data-stu-id="88161-202">Optional: Self-service group management is enabled for specific Azure AD security and Office 365 groups</span></span>

<span data-ttu-id="88161-203">그룹이 셀프 서비스 관리에 적합한지 확인하고, 해당 소유자에게 그룹 관리 워크플로 및 책임을 알리고, 그룹에 대해 [Azure AD에서 셀프 서비스 관리를 설정](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-203">You've determined which groups are appropriate for self-service management, instructed their owners on group management workflow and responsibilities, and [set up self-service management in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management) for those groups.</span></span>

<span data-ttu-id="88161-204">이 옵션을 건너뛰면 모든 Azure AD 그룹 관리 작업을 IT 관리자가 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-204">If you skip this option, all Azure AD group management tasks must be done by IT administrators.</span></span>

<span data-ttu-id="88161-205">필요한 경우 [5단계](../identity-use-group-management.md#identity-self-service-groups)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-205">If needed, [Step 5](../identity-use-group-management.md#identity-self-service-groups) can help you with this option.</span></span>

#### <a name="how-to-test"></a><span data-ttu-id="88161-206">테스트하는 방법</span><span class="sxs-lookup"><span data-stu-id="88161-206">How to test</span></span>
1.  <span data-ttu-id="88161-207">Azure Portal을 통해 Azure AD에서 테스트 사용자 계정을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="88161-207">Create a test user account in Azure AD with the Azure portal.</span></span>
2.  <span data-ttu-id="88161-208">테스트 사용자 계정으로 로그인하여 테스트 Azure AD 보안 그룹을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="88161-208">Sign-in as with the test user account and create a test Azure AD security group.</span></span>
3.  <span data-ttu-id="88161-209">로그아웃했다가 IT 관리자 계정으로 다시 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-209">Sign out and then sign-in with your IT administrator account.</span></span>
4.  <span data-ttu-id="88161-210">테스트 사용자 계정에 대한 셀프 서비스 관리를 위해 테스트 보안 그룹을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-210">Configure the test security group for self-service management for the test user account.</span></span>
5.  <span data-ttu-id="88161-211">로그아웃했다가 테스트 사용자 계정으로 다시 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-211">Sign out and then sign-in with your test user account.</span></span>
6.  <span data-ttu-id="88161-212">Azure Portal을 사용하여 테스트 보안 그룹에 구성원을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-212">Use the Azure portal to add members to the test security group.</span></span>
7.  <span data-ttu-id="88161-213">테스트 보안 그룹과 테스트 사용자 계정을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-213">Delete the test security group and the test user account.</span></span>

<a name="crit-identity-dyn-groups"></a>
### <a name="optional-dynamic-group-membership-settings-automatically-add-user-accounts-to-groups-based-on-user-account-attributes"></a><span data-ttu-id="88161-214">선택: 사용자 계정 특성에 따라 사용자 계정을 그룹에 자동으로 추가하는 동적 그룹 구성원 설정</span><span class="sxs-lookup"><span data-stu-id="88161-214">Optional: Dynamic group membership settings automatically add user accounts to groups based on user account attributes</span></span>

<span data-ttu-id="88161-215">Azure AD 동적 그룹 집합을 확인하고 [Azure Active Directory의 특성 기반 동적 그룹 구성원](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)의 지침을 사용하여 그룹과 함께 사용자 계정 특성 및 그룹 구성원 값 집합을 결정하는 규칙을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-215">You've determined the set of Azure AD dynamic groups and used the instructions in [Attribute-based dynamic group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal) to create the groups and the rules that determine the set of user account attributes and values for group membership.</span></span>

<span data-ttu-id="88161-p110">이 옵션을 건너뛰면 새 계정이 추가되거나 시간이 지남에 따라 사용자 계정 특성이 변경될 때 그룹 구성원을 수동으로 구성해야 합니다. 예를 들어 누군가 영업 부서에서 회계 부서로 이동한 경우 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-p110">If you skip this option, group membership must be done manually as new accounts are added or as user account attributes change over time. For example, if someone moves from the Sales department to the Accounting department, you must:</span></span>

- <span data-ttu-id="88161-218">해당 사용자 계정에 대한 Department 특성 값 업데이트</span><span class="sxs-lookup"><span data-stu-id="88161-218">Update the value of the Department attribute for that user account.</span></span>
- <span data-ttu-id="88161-219">영업 그룹에서 해당 사용자를 수동으로 제거</span><span class="sxs-lookup"><span data-stu-id="88161-219">Manually remove them from the Sales group.</span></span>
- <span data-ttu-id="88161-220">회계 그룹에 해당 사용자를 수동으로 추가</span><span class="sxs-lookup"><span data-stu-id="88161-220">Manually add them to the Accounting group.</span></span>

<span data-ttu-id="88161-221">영업 및 회계 그룹이 동적인 경우 사용자 계정의 부서 값만 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-221">If the Sales and Accounting groups were dynamic, you would only have to change the user account’s Department value.</span></span>

<span data-ttu-id="88161-222">필요한 경우 [5단계](../identity-use-group-management.md#identity-dyn-groups)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-222">If needed, [Step 5](../identity-use-group-management.md#identity-dyn-groups) can help you with this option.</span></span>

#### <a name="how-to-test"></a><span data-ttu-id="88161-223">테스트하는 방법</span><span class="sxs-lookup"><span data-stu-id="88161-223">How to test</span></span>

1. <span data-ttu-id="88161-224">Azure Portal을 통해 Azure AD에서 테스트 동적 그룹을 만들고 Department = "test1"에 대한 규칙을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-224">Create a test dynamic group in Azure AD with the Azure portal and configure a rule for the Department equals “test1”.</span></span>
2. <span data-ttu-id="88161-225">Azure AD에서 테스트 사용자 계정을 만들고 Department 속성을 "test1"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-225">Create a test user account in Azure AD and set the Department property to “test1”.</span></span>
3. <span data-ttu-id="88161-226">사용자 계정의 속성을 검사하여 테스트 동적 그룹의 구성원이 변경되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-226">Examine the properties of the user account to ensure that it was made a member of the test dynamic group.</span></span>
4. <span data-ttu-id="88161-227">테스트 사용자 계정에 대한 Department 속성 값을 "test2"로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-227">Change the value of the Department property for the test user account to “test2”.</span></span>
5. <span data-ttu-id="88161-228">사용자 계정의 속성을 검사하여 더 이상 테스트 동적 그룹의 구성원이 아닌지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-228">Examine the properties of the user account to ensure that it is no longer a member of the test dynamic group.</span></span>
6. <span data-ttu-id="88161-229">테스트 동적 그룹과 테스트 사용자 계정을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-229">Delete the test dynamic group and the test user account.</span></span>

<a name="crit-identity-group-license"></a>
### <a name="optional-group-based-licensing-to-automatically-assign-and-remove-licenses-to-user-accounts-based-on-group-membership"></a><span data-ttu-id="88161-230">선택: 그룹 구성원을 기반으로 사용자 계정에 라이선스를 자동으로 할당하고 제거하는 그룹 기반 라이선싱</span><span class="sxs-lookup"><span data-stu-id="88161-230">Optional: Group-based licensing to automatically assign and remove licenses to user accounts based on group membership</span></span>

<span data-ttu-id="88161-231">Microsoft 365 Enterprise 라이선스가 자동으로 할당되거나 할당 해제되도록 적절한 Azure AD 보안 그룹에 대해 [그룹 기반 라이선싱을 사용하도록 설정](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-231">You [enabled group-based licensing](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal) for the appropriate Azure AD security groups so that your Microsoft 365 Enterprise licenses are automatically assigned or unassigned.</span></span>

<span data-ttu-id="88161-232">이 옵션을 건너뛰면 다음 작업을 수동으로 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-232">If you skip this option, you must manually:</span></span>

- <span data-ttu-id="88161-233">액세스 권한을 부여하려는 새 사용자에게 라이선스를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-233">Assign licenses to new users whom you intend to have access.</span></span>
- <span data-ttu-id="88161-234">더 이상 조직과 관련이 없거나 액세스 권한이 없는 사용자로부터 라이선스를 할당 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-234">Unassign licenses from users who are no longer with your organization or do not have access.</span></span>

<span data-ttu-id="88161-235">필요한 경우 [5단계](../identity-use-group-management.md#identity-group-license)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-235">If needed, [Step 5](../identity-use-group-management.md#identity-group-license) can help you with this option.</span></span>

#### <a name="how-to-test"></a><span data-ttu-id="88161-236">테스트하는 방법</span><span class="sxs-lookup"><span data-stu-id="88161-236">How to test</span></span>

1. <span data-ttu-id="88161-237">Azure Portal을 통해 Azure AD에서 테스트 보안 그룹을 만들고 Microsoft 365 Enterprise 라이선스를 할당하도록 그룹 기반 라이선싱을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-237">Create a test security group in Azure AD with the Azure portal and configure group-based licensing to assign Microsoft 365 Enterprise license.</span></span>
2. <span data-ttu-id="88161-238">Azure AD에서 테스트 사용자 계정을 만들고 테스트 보안 그룹에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-238">Create a test user account in Azure AD and add it to the test security group.</span></span>
3. <span data-ttu-id="88161-239">Microsoft 365 관리 센터에서 사용자 계정의 속성을 검사하여 Microsoft 365 Enterprise 라이선스가 할당되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-239">Examine the properties of the user account in the Microsoft 365 admin center to ensure that it was assigned the Microsoft 365 Enterprise license.</span></span>
4. <span data-ttu-id="88161-240">테스트 보안 그룹에서 테스트 사용자 계정을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-240">Remove the test user account from the test security group.</span></span>
5. <span data-ttu-id="88161-241">사용자 계정의 속성을 검사하여 Microsoft 365 Enterprise 라이선스가 더 이상 할당되지 않았는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-241">Examine the properties of the user account to ensure that it no longer has the Microsoft 365 Enterprise license assigned.</span></span>
6. <span data-ttu-id="88161-242">테스트 보안 그룹과 테스트 사용자 계정을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-242">Delete the test security group and the test user account.</span></span>


<a name="crit-identity-access-reviews"></a>
### <a name="optional-access-reviews-configured-and-being-used-to-monitor-access"></a><span data-ttu-id="88161-243">선택: 액세스 검토를 구성하고 액세스를 모니터링하는 데 사용</span><span class="sxs-lookup"><span data-stu-id="88161-243">Optional: Access reviews configured and being used to monitor access</span></span>

<span data-ttu-id="88161-244">다음 문서를 사용하여 그룹 구성원 자격, 엔터프라이즈 애플리케이션에 대한 액세스 및 역할 할당을 모니터링하도록 다양한 유형의 액세스 검토를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88161-244">You have used these articles to configure different types of access reviews to monitor group memberships, access to enterprise applications, and role assignments:</span></span>

- [<span data-ttu-id="88161-245">그룹 및 앱</span><span class="sxs-lookup"><span data-stu-id="88161-245">Groups and apps</span></span>](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [<span data-ttu-id="88161-246">Azure AD 역할</span><span class="sxs-lookup"><span data-stu-id="88161-246">Azure AD roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [<span data-ttu-id="88161-247">Azure 리소스 역할</span><span class="sxs-lookup"><span data-stu-id="88161-247">Azure resource roles</span></span>](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

<span data-ttu-id="88161-248">필요한 경우 [6단계](../identity-configure-identity-governance.md#identity-access-reviews)를 통해 이 옵션을 충족할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88161-248">If needed, [Step 6](../identity-configure-identity-governance.md#identity-access-reviews) can help you with this option.</span></span>
