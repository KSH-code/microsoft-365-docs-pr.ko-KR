---
title: 손상된 전자 메일 계정에 응답
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.collection:
- o365_security_incident_response
- M365-security-compliance
- m365solution-smb
ms.custom:
- TopSMBIssues
- seo-marvel-apr2020
localization_priority: Priority
search.appverid:
- MET150
description: Microsoft 365에서 제공하는 도구를 사용하여 손상된 전자 메일 계정을 인식하고 대처하는 방법에 대해 알아봅니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1bbd607386b49b45ebd7444c4a91d05e4cee475b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288612"
---
# <a name="responding-to-a-compromised-email-account"></a><span data-ttu-id="c03f9-103">손상된 전자 메일 계정에 응답</span><span class="sxs-lookup"><span data-stu-id="c03f9-103">Responding to a Compromised Email Account</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c03f9-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="c03f9-104">**Applies to**</span></span>
- [<span data-ttu-id="c03f9-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c03f9-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c03f9-106">Office 365용 Microsoft Defender 플랜 1 및 플랜 2</span><span class="sxs-lookup"><span data-stu-id="c03f9-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="c03f9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c03f9-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="c03f9-108">**요약** Microsoft 365에서 손상된 전자 메일 계정을 인식하고 응답하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-108">**Summary** Learn how to recognize and respond to a compromised email account in Microsoft 365.</span></span>

## <a name="what-is-a-compromised-email-account-in-microsoft-365"></a><span data-ttu-id="c03f9-109">Microsoft 365에서 손상된 전자 메일 계정이란?</span><span class="sxs-lookup"><span data-stu-id="c03f9-109">What is a Compromised Email Account in Microsoft 365?</span></span>

<span data-ttu-id="c03f9-110">Microsoft 365 사서함, 데이터 및 기타 서비스에 대한 액세스는 자격 증명(예: 사용자 이름, 암호, PIN)을 사용하여 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-110">Access to Microsoft 365 mailboxes, data and other services, is controlled through the use of credentials, for example a user name and password or PIN.</span></span> <span data-ttu-id="c03f9-111">의도된 사용자가 아닌 사용자가 해당 자격 증명을 도용하면 도난된 자격 증명이 손상된 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-111">When someone other than the intended user steals those credentials, the stolen credentials are considered to be compromised.</span></span> <span data-ttu-id="c03f9-112">도난된 자격 증명으로 공격자는 원래 사용자로 로그인하여 불법적인 행동을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-112">With them the attacker can sign in as the original user and perform illicit actions.</span></span>
<span data-ttu-id="c03f9-113">공격자는 도난된 자격 증명을 사용하여 사용자의 Microsoft 365 사서함, SharePoint 폴더 또는 사용자의 OneDrive에 있는 파일에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-113">Using the stolen credentials, the attacker can access the user's Microsoft 365 mailbox, SharePoint folders, or files in the user's OneDrive.</span></span> <span data-ttu-id="c03f9-114">흔히 볼 수 있는 한 가지 조치는 침입자가 전자 메일을 원래 사용자로 보내 조직 내부와 외부의 받는 사람에게 보내는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-114">One action commonly seen is the attacker sending emails as the original user to recipients both inside and outside of the organization.</span></span> <span data-ttu-id="c03f9-115">공격자가 외부 수신자에게 데이터를 메일로 보낼 때 이것을 데이터 유출이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-115">When the attacker emails data to external recipients, this is called data exfiltration.</span></span>

## <a name="symptoms-of-a-compromised-microsoft-email-account"></a><span data-ttu-id="c03f9-116">손상된 Microsoft 전자 메일 계정의 증상</span><span class="sxs-lookup"><span data-stu-id="c03f9-116">Symptoms of a Compromised Microsoft Email Account</span></span>

<span data-ttu-id="c03f9-117">사용자는 Microsoft 365 사서함에서 비정상적인 활동을 알아차리고 보고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-117">Users might notice and report unusual activity in their Microsoft 365 mailboxes.</span></span> <span data-ttu-id="c03f9-118">몇 가지 일반적인 증상은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-118">Here are some common symptoms:</span></span>

- <span data-ttu-id="c03f9-119">이메일 누락 또는 삭제와 같은 의심스러운 활동</span><span class="sxs-lookup"><span data-stu-id="c03f9-119">Suspicious activity, such as missing or deleted emails.</span></span>

- <span data-ttu-id="c03f9-120">다른 사용자는 보낸 사람의 **보낸 편지함** 폴더에 해당 메일이 없어도 손상된 계정의 메일을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-120">Other users might receive emails from the compromised account without the corresponding email existing in the **Sent Items** folder of the sender.</span></span>

- <span data-ttu-id="c03f9-121">의도된 사용자 또는 관리자가 생성하지 않은 받은 편지함 규칙이 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="c03f9-121">The presence of inbox rules that weren't created by the intended user or the administrator.</span></span> <span data-ttu-id="c03f9-122">이러한 규칙은 메일을 알 수 없는 주소로 자동 전달하거나 **노트**, **정크 메일** 또는 **RSS 구독** 폴더로 이동시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-122">These rules may automatically forward emails to unknown addresses or move them to the **Notes**, **Junk Email**, or **RSS Subscriptions** folders.</span></span>

- <span data-ttu-id="c03f9-123">전체 주소 목록에서 사용자의 표시 이름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-123">The user's display name might be changed in the Global Address List.</span></span>

- <span data-ttu-id="c03f9-124">사용자의 사서함에서 메일 보내기가 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-124">The user's mailbox is blocked from sending email.</span></span>

- <span data-ttu-id="c03f9-125">Microsoft Outlook 또는 웹용 Outlook (이전까지의 Outlook Web App)에있는 보낸 편지함 또는 지운 편지함 폴더에는 "런던에 묶여 있습니다. 돈을 보내주세요."와 같은 일반적인 해킹된 계정 메시지가 들어있습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-125">The Sent or Deleted Items folders in Microsoft Outlook or Outlook on the web (formerly known as Outlook Web App) contain common hacked-account messages, such as "I'm stuck in London, send money."</span></span>

- <span data-ttu-id="c03f9-126">이름, 전화 번호 또는 우편 번호와 같은 비정상적인 프로필 변경 사항이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-126">Unusual profile changes, such as the name, the telephone number, or the postal code were updated.</span></span>

- <span data-ttu-id="c03f9-127">여러 암호 변경과 같은 비정상적인 자격 증명 변경이 요구됩니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-127">Unusual credential changes, such as multiple password changes are required.</span></span>

- <span data-ttu-id="c03f9-128">최근에 메일 전달이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-128">Mail forwarding was recently added.</span></span>

- <span data-ttu-id="c03f9-129">가짜 은행 업무 서명이나 처방약 서명과 같은 비정상적인 서명이 최근 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-129">An unusual signature was recently added, such as a fake banking signature or a prescription drug signature.</span></span>

<span data-ttu-id="c03f9-130">사용자가 위의 증상 중 하나를 보고하면 추가 조사를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-130">If a user reports any of the above symptoms, you should perform further investigation.</span></span> <span data-ttu-id="c03f9-131">Microsoft 365 보안 및 규정 준수 센터 및 Azure 포털은 손상되었을 가능성이 있는 것으로 의심되는 사용자 계정의 활동을 조사하는 데 유용한 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-131">The Microsoft 365 Security & Compliance Center and the Azure Portal offer tools to help you investigate the activity of a user account that you suspect may be compromised.</span></span>

- <span data-ttu-id="c03f9-132">**보안 및 규정 준수 센터의 통합 감사 로그**: 의심스러운 활동이 발생한 직전부터 현재 날짜까지의 기간에 대한 결과를 필터링하여 의심되는 계정에 대한 모든 활동을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-132">**Unified Audit Logs in the Security & Compliance Center**: Review all the activities for the suspected account by filtering the results for the date range spanning from immediately before the suspicious activity occurred to the current date.</span></span> <span data-ttu-id="c03f9-133">검색 중에 활동을 필터링하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="c03f9-133">Do not filter on the activities during the search.</span></span>

- <span data-ttu-id="c03f9-134">**EAC에서의 관리자 감사 로그**: Exchange Online에서 Exchange 관리 센터(EAC)를 사용하여 관리자 감사 로그 항목을 검색하고 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-134">**Admin Audit logs in the EAC**: In Exchange Online, you can use the Exchange admin center (EAC) to search for and view entries in the administrator audit log.</span></span> <span data-ttu-id="c03f9-135">관리자 감사 로그에는 관리 권한이 할당된 관리자와 사용자가 수행하는 특정 작업이 Exchange PowerShell cmdlet을 기준으로 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-135">The administrator audit log records specific actions, based on Exchange Online PowerShell cmdlets, performed by administrators and users who have been assigned administrative privileges.</span></span> <span data-ttu-id="c03f9-136">관리자 감사 로그의 항목은 실행된 cmdlet, 사용된 매개 변수, cmdlet을 실행한 사용자 및 영향을 받은 개체에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-136">Entries in the administrator audit log provide you with information about what cmdlet was run, which parameters were used, who ran the cmdlet, and what objects were affected.</span></span>

- <span data-ttu-id="c03f9-137">**Azure AD 포털의 Azure AD 로그인 로그 및 기타 위험 보고서**: 다음 열의 값을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-137">**Azure AD Sign-in logs and other risk reports in the Azure AD portal**: Examine the values in these columns:</span></span>

  - <span data-ttu-id="c03f9-138">IP 주소 검토</span><span class="sxs-lookup"><span data-stu-id="c03f9-138">Review IP address</span></span>
  - <span data-ttu-id="c03f9-139">로그인 위치</span><span class="sxs-lookup"><span data-stu-id="c03f9-139">sign-in locations</span></span>
  - <span data-ttu-id="c03f9-140">로그인 시간</span><span class="sxs-lookup"><span data-stu-id="c03f9-140">sign-in times</span></span>
  - <span data-ttu-id="c03f9-141">로그인 성공 또는 실패</span><span class="sxs-lookup"><span data-stu-id="c03f9-141">sign-in success or failure</span></span>

## <a name="how-to-secure-and-restore-email-function-to-a-suspected-compromised-microsoft-365-account-and-mailbox"></a><span data-ttu-id="c03f9-142">손상된 Microsoft 365 계정 및 사서함으로 의심되는 전자 메일 기능을 보호하고 복원하는 방법</span><span class="sxs-lookup"><span data-stu-id="c03f9-142">How to secure and restore email function to a suspected compromised Microsoft 365 account and mailbox</span></span>

> [!VIDEO https://videoplayercdn.osi.office.net/hub/?csid=ux-cms-en-us-msoffice&uuid=RE2jvOb&AutoPlayVideo=false]

<span data-ttu-id="c03f9-143">계정에 대한 액세스 권한을 회복한 후에도 공격자는 백도어 항목을 추가하여 계정을 다시 제어하기 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-143">Even after you've regained access to your account, the attacker may have added back-door entries that enable the attacker to resume control of the account.</span></span>

<span data-ttu-id="c03f9-144">계정에 대한 액세스 권한을 다시 얻으려면 다음 단계를 모두 수행해야 합니다. 계정 도용자가 계정 제어를 재개하지 않는지 확인하는 것은 빠를수록 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-144">You must do all the following steps to regain access to your account the sooner the better to make sure that the hijacker doesn't resume control your account.</span></span> <span data-ttu-id="c03f9-145">이 단계는 계정 도용자가 귀하의 계정에 추가한 백도어 항목을 제거하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-145">These steps help you remove any back-door entries that the hijacker may have added to your account.</span></span> <span data-ttu-id="c03f9-146">이러한 단계를 수행한 후에는 컴퓨터가 손상되지 않았는지 확인하기 위해 바이러스 검사를 실행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-146">After you do these steps, we recommend that you run a virus scan to make sure that your computer isn't compromised.</span></span>

### <a name="step-1-reset-the-users-password"></a><span data-ttu-id="c03f9-147">1단계 사용자의 암호 재설정하기</span><span class="sxs-lookup"><span data-stu-id="c03f9-147">Step 1 Reset the user's password</span></span>

<span data-ttu-id="c03f9-148">[다른 사람을 위해 비즈니스 암호 재설정하기](../../admin/add-users/reset-passwords.md#reset-my-admin-password)의 절차를 따르세요. </span><span class="sxs-lookup"><span data-stu-id="c03f9-148">Follow the procedures in [Reset a business password for someone](../../admin/add-users/reset-passwords.md#reset-my-admin-password).</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="c03f9-149">이 시점에서 공격자가 여전히 사서함에 액세스할 수 있으므로 메일을 통해 의도한 사용자에게 새 암호를 보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-149">Do not send the new password to the intended user through email as the attacker still has access to the mailbox at this point.</span></span>
>
> - <span data-ttu-id="c03f9-150">암호가 강하고 대문자, 소문자, 숫자 하나 이상 및 특수 문자가 하나 이상 포함되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-150">Make sure that the password is strong and that it contains upper and lowercase letters, at least one number, and at least one special character.</span></span>
>
> - <span data-ttu-id="c03f9-151">지난 마지막 5개의 암호를 다시 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-151">Don't reuse any of your last five passwords.</span></span> <span data-ttu-id="c03f9-152">암호 기록 요구 사항을 통해 최근 암호를 다시 사용할 수는 있지만 공격자가 추측할 수 없는 암호를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-152">Even though the password history requirement lets you reuse a more recent password, you should select something that the attacker can't guess.</span></span>
>
> - <span data-ttu-id="c03f9-153">온-프레미스 ID가 Microsoft 365와 페더레이션된 경우 온-프레미스 암호를 변경해야 하며 관리자에게 손상 사실을 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-153">If your on-premises identity is federated with Microsoft 365, you must change your password on-premises, and then you must notify your administrator of the compromise.</span></span>
>
> - <span data-ttu-id="c03f9-154">앱 암호를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-154">Be sure to update app passwords.</span></span> <span data-ttu-id="c03f9-155">사용자 계정 암호가 재설정되어도 앱 암호가 자동으로 취소되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-155">App passwords aren't automatically revoked when a user account password reset.</span></span> <span data-ttu-id="c03f9-156">사용자가 직접 기존 앱 암호를 삭제하고 새 암호를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-156">The user should delete existing app passwords and create new ones.</span></span> <span data-ttu-id="c03f9-157">자세한 내용은 [추가 보안 확인 페이지에서 앱 암호 만들기 및 삭제](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c03f9-157">For instructions, see [Create and delete app passwords from the Additional security verification page](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-app-passwords#create-and-delete-app-passwords-from-the-additional-security-verification-page).</span></span>
>
> - <span data-ttu-id="c03f9-158">특히 관리자 권한이있는 계정의 경우에는 손상 방지를 위해 MFA(다중 요소 인증)를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-158">We highly recommended that you enable Multi-Factor Authentication (MFA) in order to prevent compromise, especially for accounts with administrative privileges.</span></span> <span data-ttu-id="c03f9-159">MFA에 대한 자세한 내용은 [다단계 인증 설정하기로](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="c03f9-159">To learn more about MFA, go to [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

### <a name="step-2-remove-suspicious-email-forwarding-addresses"></a><span data-ttu-id="c03f9-160">2단계 의심스러운 메일 전달 주소 제거하기</span><span class="sxs-lookup"><span data-stu-id="c03f9-160">Step 2 Remove suspicious email forwarding addresses</span></span>

1. <span data-ttu-id="c03f9-161"><https://admin.microsoft.com>에서 Microsoft 365 관리 센터 열기</span><span class="sxs-lookup"><span data-stu-id="c03f9-161">Open the Microsoft 365 admin center at <https://admin.microsoft.com></span></span>

2. <span data-ttu-id="c03f9-162">**사용자** \> **활성 사용자** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-162">Go to **Users** \> **Active users**.</span></span> <span data-ttu-id="c03f9-163">해당 사용자 계정을 찾은 다음, 확인란을 선택하지 않고 사용자(행)를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-163">Find the user account in question, and select the user (row) without selecting the checkbox.</span></span>

3. <span data-ttu-id="c03f9-164">세부 정보 플라이아웃이 나타나면 **메일** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-164">In the details flyout that appears, select the **Mail** tab.</span></span>

4. <span data-ttu-id="c03f9-165">**전자 메일 전달** 구역에 있는 값이 **적용된 경우**, **전자 메일 전달 관리** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-165">If the value in the **Email forwarding** section is **Applied**, click **Manage email forwarding**.</span></span> <span data-ttu-id="c03f9-166">**전자 메일 전달 관리** 에서 플라이아웃이 표시되면, **이 사서함으로 모든 메일 전송** 을 취소하고 **변경 내용 저장** 을 클릭합니다. </span><span class="sxs-lookup"><span data-stu-id="c03f9-166">In the **Manage email forwarding** flyout that appears, clear **Forward all email sent to this mailbox**, and then click **Save changes**.</span></span>

### <a name="step-3-disable-any-suspicious-inbox-rules"></a><span data-ttu-id="c03f9-167">3단계는 의심스러운 받은 편지함 규칙을 사용하지 않도록 설정하기</span><span class="sxs-lookup"><span data-stu-id="c03f9-167">Step 3 Disable any suspicious inbox rules</span></span>

1. <span data-ttu-id="c03f9-168">웹용 Outlook을 사용하여 사용자의 사서함에 로그인합니다..</span><span class="sxs-lookup"><span data-stu-id="c03f9-168">Sign in to the user's mailbox using Outlook on the web.</span></span>

2. <span data-ttu-id="c03f9-169">기어 아이콘을 클릭하고 **메일** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-169">Click on the gear icon and click **Mail**.</span></span>

3. <span data-ttu-id="c03f9-170">**받은 편지함 및 비우기 규칙** 을 클릭하고 규칙을 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-170">Click **Inbox and sweep rules** and review the rules.</span></span>

4. <span data-ttu-id="c03f9-171">의심러운 규칙을 사용하지 않도록 설정하거나 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-171">Disable or delete suspicious rules.</span></span>

### <a name="step-4-unblock-the-user-from-sending-mail"></a><span data-ttu-id="c03f9-172">4단계 사용자 메일 보내기 차단을 해제하기</span><span class="sxs-lookup"><span data-stu-id="c03f9-172">Step 4 Unblock the user from sending mail</span></span>

<span data-ttu-id="c03f9-173">손상된 것으로 의심되는 사서함이 스팸 메일을 보내기 위해 불법적으로 사용된 경우 사서함이 메일을 보내지 못하도록 차단되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-173">If the suspected compromised mailbox was used illicitly to send spam email, it is likely that the mailbox has been blocked from sending mail.</span></span>

<span data-ttu-id="c03f9-174">메일 보내기에서 사서함을 차단 해제하려면 [스팸 전자 메일를 보낸 후 제한된 사용자 포털에서 사용자 제거](removing-user-from-restricted-users-portal-after-spam.md)의 절차를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="c03f9-174">To unblock a mailbox from sending mail, follow the procedures in [Removing a user from the Restricted Users portal after sending spam email](removing-user-from-restricted-users-portal-after-spam.md).</span></span>

### <a name="step-5-optional-block-the-user-account-from-signing-in"></a><span data-ttu-id="c03f9-175">5단계 선택 사항 : 사용자 계정 로그인을 차단하기</span><span class="sxs-lookup"><span data-stu-id="c03f9-175">Step 5 Optional: Block the user account from signing-in</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c03f9-176">액세스가 다시 활성화되어도 안전하다고 판단될 때까지 손상된 것으로 의심되는 계정이 로그인하지 못하도록 차단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-176">You can block the suspected compromised account from signing-in until you believe it is safe to re-enable access.</span></span>

1. <span data-ttu-id="c03f9-177">Microsoft 365 관리 센터를 열고 **사용자** \> **활성 사용자** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-177">Open the Microsoft 365 admin center and go to **Users** \> **Active users**.</span></span>

2. <span data-ttu-id="c03f9-178">사용자 계정을 찾아 선택하고 ![아이콘 더 보기](../../media/ITPro-EAC-MoreOptionsIcon.png)를 클릭한 다음 **로그인 상태 편집** 을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-178">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Edit sign-in status**.</span></span>

3. <span data-ttu-id="c03f9-179">표시 되는 **로그인 차단** 창에서 **해당 사용자 로그인 차단** 을 선택한 다음 **변경 내용 저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-179">On the **Block sign-in** pane that appears, select **Block this user from signing in**, and then click **Save changes**.</span></span>

4. <span data-ttu-id="c03f9-180"><admin.protection.outlook.com/ecp/>에서 Exchange 관리 센터(EAC)를 열고 **수신자 > 사서함** 으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-180">Open the Exchange admin center (EAC) at <admin.protection.outlook.com/ecp/>, and go to **Recipients > Mailboxes**.</span></span>

5. <span data-ttu-id="c03f9-181">사용자를 찾아 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-181">Find and select the select the user.</span></span> <span data-ttu-id="c03f9-182">세부 정보 창에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-182">In the details pane, do the following steps:</span></span>

   - <span data-ttu-id="c03f9-183">**전화 및 음성 기능** 구역에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-183">In the **Phone and voice features** section, do the following steps:</span></span>

     - <span data-ttu-id="c03f9-184">**Exchange ActiveSync 사용 안 함** 을 선택한 다음 표시되는 경고에서 **예** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-184">Select **Disable Exchange ActiveSync** and then click **Yes** in the warning that appears.</span></span>
     - <span data-ttu-id="c03f9-185">**디바이스용 OWA 사용 안 함** 을 선택한 다음 표시되는 경고에서 **예** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-185">Select **Disable OWA for Devices** and then click **Yes** in the warning that appears.</span></span>

   - <span data-ttu-id="c03f9-186">웹용 Outlook의 **전자 메일 연결** 구역에서 **해제** 를 클릭한 다음 표시되는 경고에서 **예** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-186">In the **Email Connectivity** section for Outlook on the web, click **Disable** and then click **Yes** in the warning that appears.</span></span>

### <a name="step-6-optional-remove-the-suspected-compromised-account-from-all-administrative-role-groups"></a><span data-ttu-id="c03f9-187">6단계 선택 사항: 모든 관리 역할 그룹에서 손상된 것으로 의심되는 계정 제거하기</span><span class="sxs-lookup"><span data-stu-id="c03f9-187">Step 6 Optional: Remove the suspected compromised account from all administrative role groups</span></span>

> [!NOTE]
> <span data-ttu-id="c03f9-188">관리 역할 그룹 구성원은 계정이 보안된 후에 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-188">Administrative role group membership can be restored after the account has been secured.</span></span>

1. <span data-ttu-id="c03f9-189">전역 관리자 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-189">Sign in with a global administrator account:</span></span>

2. <span data-ttu-id="c03f9-190">Microsoft 365 관리 센터에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-190">In the Microsoft 365 admin center, do the following steps:</span></span>

   1. <span data-ttu-id="c03f9-191">**사용자** \> **활성 사용자** 로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-191">Go to **Users** \> **Active users**.</span></span>
   2. <span data-ttu-id="c03f9-192">사용자 계정을 찾아 선택하고 ![아이콘 더 보기](../../media/ITPro-EAC-MoreOptionsIcon.png)를 클릭한 다음 **역할 관리** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-192">Find and select the user account, click ![More icon](../../media/ITPro-EAC-MoreOptionsIcon.png), and then select **Manage roles**.</span></span>
   3. <span data-ttu-id="c03f9-193">계정에 할당된 모든 관리 역할을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-193">Remove any administrative roles that are assigned to the account.</span></span> <span data-ttu-id="c03f9-194">작업을 마쳤으면 **변경 내용 저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-194">When you're finished, click **Save changes**.</span></span>

3. <span data-ttu-id="c03f9-195"><https://protection.office.com>의 보안 및 규정 준수 센터에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-195">In the Security & Compliance Center at <https://protection.office.com>, do the following steps:</span></span>

   <span data-ttu-id="c03f9-196">**사용 권한** 을 선택하고 목록에서 각 역할 그룹을 선택한 다음 표시되는 세부 정보 플라이아웃의 **구성원** 구역에서 사용자 계정을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-196">Select **Permissions**, select each role group in the list and look for the user account in the **Members** section of the details flyout that appears.</span></span> <span data-ttu-id="c03f9-197">역할 그룹에 사용자 계정이 포함되어 있는 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-197">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="c03f9-198">a.</span><span class="sxs-lookup"><span data-stu-id="c03f9-198">a.</span></span> <span data-ttu-id="c03f9-199">**구성원** 옆에 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-199">Click **Edit** next to **Members**.</span></span>
   <span data-ttu-id="c03f9-200">b.</span><span class="sxs-lookup"><span data-stu-id="c03f9-200">b.</span></span> <span data-ttu-id="c03f9-201">표시되는 **구성원 선택 편집** 플라이아웃에서 **편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-201">On the **Editing Choose members** flyout that appears, click **Edit**.</span></span>
   <span data-ttu-id="c03f9-202">c.</span><span class="sxs-lookup"><span data-stu-id="c03f9-202">c.</span></span> <span data-ttu-id="c03f9-203">표시되는 **구성원 선택** 플라이아웃에서 사용자 계정을 선택하고 **제거** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-203">In the **Choose members** flyout that appears, select the user account, and then click **Remove**.</span></span> <span data-ttu-id="c03f9-204">작업을 마쳤으면 **완료**, **저장**, 그 다음 **종료** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-204">When you're finished, click **Done**, **Save**, and then **Close**.</span></span>

4. <span data-ttu-id="c03f9-205"><admin.protection.outlook.com/ecp/>의 EAC에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-205">In the EAC at <admin.protection.outlook.com/ecp/>, do the following steps:</span></span>

   <span data-ttu-id="c03f9-206">**사용 권한** 을 선택하고 수동으로 역할 그룹을 선택한 다음, 세부 정보 창에서 **구성원** 구역에 있는 사용자 계정을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-206">Select **Permissions**, manually select each role group, and in the details pane, verify the user accounts in the **Members** section.</span></span>  <span data-ttu-id="c03f9-207">역할 그룹에 사용자 계정이 포함되어 있는 경우 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-207">If the role group contains the user account, do the following steps:</span></span>

   <span data-ttu-id="c03f9-208">a.</span><span class="sxs-lookup"><span data-stu-id="c03f9-208">a.</span></span> <span data-ttu-id="c03f9-209">역할 그룹을 선택하고고 **편집** ![아이콘 편집](../../media/ITPro-EAC-EditIcon.png)을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-209">Select the role group, click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span>
   <span data-ttu-id="c03f9-210">b.</span><span class="sxs-lookup"><span data-stu-id="c03f9-210">b.</span></span> <span data-ttu-id="c03f9-211">**구성원** 구역에서 사용자 계정을 선택한 다음 **제거** ![아이콘 제거](../../media/ITPro-EAC-RemoveIcon.gif)를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-211">In the **Member** section, select the user account, and then click **Remove** ![Remove icon](../../media/ITPro-EAC-RemoveIcon.gif).</span></span> <span data-ttu-id="c03f9-212">작업을 마쳤으면 **저장** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-212">When you're finished, click **Save**.</span></span>

### <a name="step-7-optional-additional-precautionary-steps"></a><span data-ttu-id="c03f9-213">7단계 선택 사항 : 추가 예비 단계</span><span class="sxs-lookup"><span data-stu-id="c03f9-213">Step 7 Optional: Additional precautionary steps</span></span>

1. <span data-ttu-id="c03f9-214">보낸된 항목을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-214">Make sure that you verify your sent items.</span></span> <span data-ttu-id="c03f9-215">연락처 목록에 있는 사람들에게 계정이 손상되었다는 사실을 알려야할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-215">You may have to inform people on your contacts list that your account was compromised.</span></span> <span data-ttu-id="c03f9-216">공격자가 돈을 요구했을 수 있습니다. 예를 들어, 다른 국가에 묶여 돈이 필요하거나, 공격자가 컴퓨터를 도용하기 위해 바이러스를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-216">The attacker may have asked them for money, spoofing, for example, that you were stranded in a different country and needed money, or the attacker may send them a virus to also hijack their computers.</span></span>

2. <span data-ttu-id="c03f9-217">이 Exchange 계정을 대체 메일 계정으로 사용한 다른 서비스가 손상되었을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-217">Any other service that used this Exchange account as its alternative email account may have been compromised.</span></span> <span data-ttu-id="c03f9-218">먼저 Microsoft 365 구독에 대해 이러한 단계를 수행한 다음 다른 계정에 대해 이 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-218">First, do these steps for your Microsoft 365 subscription, and then do these steps for your other accounts.</span></span>

3. <span data-ttu-id="c03f9-219">전화번호 및 주소와 같은 연락처 정보가 정확한지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-219">Make sure that your contact information, such as telephone numbers and addresses, is correct.</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="c03f9-220">사이버 보안 프로그램과 같은 Microsoft 365 보안</span><span class="sxs-lookup"><span data-stu-id="c03f9-220">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="c03f9-221">Microsoft 365 구독에는 데이터 및 사용자를 보호하는 데 사용할 수 있는 강력한 보안 기능이 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-221">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="c03f9-222">[Microsoft 365 보안 로드맵 - 최초 30일, 90일 및 그 이후의 최우선 순위](security-roadmap.md)를 사용하여 Microsoft에서 권장하는 Microsoft 365 테넌트 보안을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-222">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="c03f9-223">처음 30일 이내에 수행 할 작업</span><span class="sxs-lookup"><span data-stu-id="c03f9-223">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="c03f9-224">이러한 작업들은 즉각적인 영향을 미치며 사용자에게 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-224">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="c03f9-225">90일 이내에 수행해야 할 작업</span><span class="sxs-lookup"><span data-stu-id="c03f9-225">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="c03f9-226">이러한 작업들은 계획하고 구현하는 데 다소 시간이 걸리지만 보안 태세를 갖추는 데 큰 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-226">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="c03f9-227">90일 초과</span><span class="sxs-lookup"><span data-stu-id="c03f9-227">Beyond 90 days.</span></span> <span data-ttu-id="c03f9-228">이러한 향상된 기능은 처음 90일간의 작업에서 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="c03f9-228">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="c03f9-229">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c03f9-229">See also</span></span>

- [<span data-ttu-id="c03f9-230">Microsoft 365에서 Outlook 규칙 및 사용자 지정 양식 주입 공격 감지 및 재구성</span><span class="sxs-lookup"><span data-stu-id="c03f9-230">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Microsoft 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

- [<span data-ttu-id="c03f9-231">인터넷 범죄 불만 센터</span><span class="sxs-lookup"><span data-stu-id="c03f9-231">Internet Crime Complaint Center</span></span>](https://www.ic3.gov/preventiontips.aspx)

- [<span data-ttu-id="c03f9-232">증권 거래 위원회 - “피싱” 사기</span><span class="sxs-lookup"><span data-stu-id="c03f9-232">Securities and Exchange Commission - "Phishing" Fraud</span></span>](https://www.sec.gov/investor/pubs/phishing.htm)

- <span data-ttu-id="c03f9-233">Microsoft와 관리자에게 스팸 전자 메일을 직접 보고하려면 [보고서 메시지 추가 기능을 사용하세요](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).</span><span class="sxs-lookup"><span data-stu-id="c03f9-233">To report spam email directly to Microsoft and your admin [Use the Report Message add-in](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)</span></span>
