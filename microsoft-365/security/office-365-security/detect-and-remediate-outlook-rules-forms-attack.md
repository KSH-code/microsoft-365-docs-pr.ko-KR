---
title: Outlook 규칙 및 사용자 지정 양식 주입 공격을 감지하고 수정합니다.
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyp
manager: dansimp
ms.date: 04/23/2018
audience: ITPro
ms.topic: article
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: Office 365에서 Outlook 규칙 및 사용자 지정 양식 주입 공격을 인지하고 재구성하는 방법 알아보기
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e22cfa97ae59fdd094c161cdaeff899dc1dd6507
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286396"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a><span data-ttu-id="97394-103">Outlook 규칙 및 사용자 지정 양식 주입 공격 감지 및 수정</span><span class="sxs-lookup"><span data-stu-id="97394-103">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="97394-104">**요약** Office 365에서 Outlook 규칙 및 사용자 지정 양식 주입 공격을 인지하고 재구성하는 방법 알아보기</span><span class="sxs-lookup"><span data-stu-id="97394-104">**Summary** Learn how to recognize and remediate the Outlook rules and custom Forms injections attacks in Office 365.</span></span>

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a><span data-ttu-id="97394-105">Outlook 규칙과 사용자 지정 양식 주입 공격은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="97394-105">What is the Outlook Rules and Custom Forms injection attack?</span></span>

<span data-ttu-id="97394-106">공격자는 테넌트에서 계정을 침해하고 침범한 후에 검색되고 제거된 후 계정에 머무르거나 다시 돌아올 방법을 시도하고 설정할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="97394-106">After an attacker has breached an account in your tenancy and gets in, they're are going to try and establish a way to stay in or a way to get back in after they are discovered and removed.</span></span> <span data-ttu-id="97394-107">이를 지속성 메커니즘을 설정이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-107">This is called establishing a persistence mechanism.</span></span> <span data-ttu-id="97394-108">이 작업을 수행할 수 있는 두 가지 방법은 Outlook 규칙을 활용하거나 Outlook에 사용자 지정 양식을 주입하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="97394-108">Two ways that they can do this are by exploiting Outlook rules or by injecting custom forms into Outlook.</span></span>
<span data-ttu-id="97394-109">두 경우 모두 해당 규칙이나 양식이 클라우드 서비스에서 데스크톱 클라이언트로 동기화되므로 클라이언트 소프트웨어를 완벽하게 포맷하고 다시 설치하여도 주입 메커니즘을 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-109">In both cases, the rule or form is synced from the cloud service down to the desktop client, so a full format and re-install of the client software doesn't eliminate the injection mechanism.</span></span> <span data-ttu-id="97394-110">이는 Outlook 클라이언트 소프트웨어가 클라우드의 사서함에 다시 연결하는 경우 클라우드에서 규칙과 양식이 다시 다운로드되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="97394-110">This is because when the Outlook client software reconnects to the mailbox in the cloud it will re-download the rules and forms from the cloud.</span></span> <span data-ttu-id="97394-111">규칙과 양식이 준비되면 공격자는 이를 사용하 여 원격 또는 사용자 지정 코드를 실행하여 일반적으로 로컬 컴퓨터에 맬웨어를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-111">Once the rules and forms are in place, the attacker uses them to execute remote or custom code, usually to install malware on the local machine.</span></span> <span data-ttu-id="97394-112">그런 다음 맬웨어는 자격 증명을 다시 도용하거나 다른 불법 활동을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-112">The malware then re-steals credentials or performs other illicit activity.</span></span>
<span data-ttu-id="97394-113">여기서 좋은 소식은 클라이언트를 최신 버전으로 유지하면 현재 Outlook 클라이언트 기본값으로 이 두 가지 메커니즘을 차단함에 따라 위협에 취약하지 않다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="97394-113">The good news here is that if you keep your clients patched to the latest version, you are not vulnerable to the threat as current Outlook client defaults block both mechanisms.</span></span>

<span data-ttu-id="97394-114">이 공격은 일반적으로 다음의 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="97394-114">The attacks typically follow these patterns:</span></span>

<span data-ttu-id="97394-115">**규칙 활용**:</span><span class="sxs-lookup"><span data-stu-id="97394-115">**The Rules Exploit**:</span></span>

1. <span data-ttu-id="97394-116">공격자는 사용자 가운데 한 명의 사용자 이름과 암호를 도용합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-116">The attacker steals the username and password of one of your users.</span></span>

2. <span data-ttu-id="97394-117">그런 다음 공격자는 해당 사용자의 Exchange 사서함에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-117">The attacker then signs in to that users Exchange mailbox.</span></span> <span data-ttu-id="97394-118">사서함은 Exchange Online에 있거나 Exchange 온-프레미스에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-118">The mailbox can either be in Exchange online or in Exchange on-premises.</span></span>

3. <span data-ttu-id="97394-119">그런 다음 공격자는 사서함에서 규칙 조건과 일치하는 전자 메일을 받을 때 트리거되는 사서함에 전달 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="97394-119">The attacker then creates a forwarding rule in the mailbox that is triggered when the mailbox receives an email that matches the criteria of the rule.</span></span> <span data-ttu-id="97394-120">규칙과 트리거 전자 메일의 조건은 서로에 맞게 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="97394-120">The criteria of rule and the contents of the trigger email are tailor-made for each other.</span></span>

4. <span data-ttu-id="97394-121">공격자는 자신의 사서함을 일반적으로 사용하는 사용자에게 트리거 전자 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="97394-121">The attacker sends the trigger email to the user who is using their mailbox normally.</span></span>

5. <span data-ttu-id="97394-122">전자 메일을 받으면 규칙이 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="97394-122">When the email is received, the rule is triggered.</span></span> <span data-ttu-id="97394-123">규칙의 작동은 대개 원격(WebDAV) 서버에서 응용 프로그램을 시작하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="97394-123">The action of the rule is usually to launch an application on a remote (WebDAV) server.</span></span>

6. <span data-ttu-id="97394-124">일반적으로 응용 프로그램은 사용자 컴퓨터에 로컬로 [Powershell Empire](https://www.powershellempire.com/)와 같은 맬웨어를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-124">The application typically installs malware, such as [Powershell Empire](https://www.powershellempire.com/), locally on the user's machine.</span></span>

7. <span data-ttu-id="97394-125">공격자는 이 맬웨어를 사용하여 로컬 컴퓨터에서 사용자의 사용자 이름과 암호 혹은 기타 자격 증명을 다시 도용하고 다른 악의적인 활동을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-125">The malware allows the attacker to re-steal the user's username and password or other credentials from local machine and perform other malicious activities.</span></span>

<span data-ttu-id="97394-126">**양식 활용**:</span><span class="sxs-lookup"><span data-stu-id="97394-126">**The Forms Exploit**:</span></span>

1. <span data-ttu-id="97394-127">공격자는 사용자 가운데 한 명의 사용자 이름과 암호를 도용합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-127">The attacker steals the username and password of one of your users.</span></span>

2. <span data-ttu-id="97394-128">그런 다음 공격자는 해당 사용자의 Exchange 사서함에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-128">The attacker then sign in to that users Exchange mailbox.</span></span> <span data-ttu-id="97394-129">사서함은 Exchange Online에 있거나 Exchange 온-프레미스에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-129">The mailbox can either be in Exchange online or in Exchange on-premises.</span></span>

3. <span data-ttu-id="97394-130">그런 다음 공격자는 사용자 지정 메일 양식 서식 파일을 만들어 사용자의 사서함에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-130">The attacker then creates a custom mail form template and inserts it into the user's mailbox.</span></span> <span data-ttu-id="97394-131">사용자 지정 양식은 사서함이 사용자 지정 양식을 로드해야 하는 전자 메일을 받을 때 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="97394-131">The custom form is triggered when the mailbox receives an email that requires the mailbox to load the custom form.</span></span> <span data-ttu-id="97394-132">사용자 지정 양식과 전자 메일 서식은 서로에 맞게 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="97394-132">The custom form and the format of email are tailor-made for each other.</span></span>
4. <span data-ttu-id="97394-133">공격자는 자신의 사서함을 일반적으로 사용하는 사용자에게 트리거 전자 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="97394-133">The attacker sends the trigger email to the user, who is using their mailbox normally.</span></span>

5. <span data-ttu-id="97394-134">전자 메일을 받으면 양식이 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="97394-134">When the email is received, the form is loaded.</span></span> <span data-ttu-id="97394-135">양식은 원격(WebDAV) 서버에서 응용 프로그램을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-135">The form launches an application on a remote (WebDAV) server.</span></span>

6. <span data-ttu-id="97394-136">일반적으로 응용 프로그램은 사용자 컴퓨터에 로컬로 [Powershell Empire](https://www.powershellempire.com/)와 같은 맬웨어를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-136">The application typically installs malware, such as [Powershell Empire](https://www.powershellempire.com/), locally on the user's machine.</span></span>

7. <span data-ttu-id="97394-137">공격자는 이 맬웨어를 사용하여 로컬 컴퓨터에서 사용자의 사용자 이름과 암호 혹은 기타 자격 증명을 다시 도용하고 다른 악의적인 활동을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-137">The malware allows the attacker to re-steal the user's username and password or other credentials from local machine and perform other malicious activities.</span></span>

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a><span data-ttu-id="97394-138">어떠한 규칙 및 사용자 지정 양식 주입 공격이 Office 365와 같아 보일 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="97394-138">What a Rules and Custom Forms Injection attack might look like Office 365?</span></span>

<span data-ttu-id="97394-139">이러한 지속성 메커니즘은 사용자가 발견할 가능성이 거의 없으며 일부의 경우에 보이지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-139">These persistence mechanisms are unlikely to be noticed by your users and may in some cases even be invisible to them.</span></span> <span data-ttu-id="97394-140">이 문서에서는 아래에 나열된 7가지 기호(위험 노출 표시기)를 찾는 방법을 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="97394-140">This article tells you how to look for any of the seven signs (Indicators of Compromise) listed below.</span></span> <span data-ttu-id="97394-141">이러한 내용을 발견하면 재구성 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-141">If you find any of these, you need to take remediation steps.</span></span>

- <span data-ttu-id="97394-142">규칙 위험 노출 표시기:</span><span class="sxs-lookup"><span data-stu-id="97394-142">Indicators of the Rules compromise:</span></span>

  - <span data-ttu-id="97394-143">규칙 작업은 응용 프로그램을 시작하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="97394-143">Rule Action is to start an application.</span></span>

  - <span data-ttu-id="97394-144">규칙에서 EXE, ZIP 또는 URL을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-144">Rule References an EXE, ZIP, or URL.</span></span>

  - <span data-ttu-id="97394-145">로컬 컴퓨터에서 Outlook PID가 보낸 새 프로세스 시작을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-145">On the local machine, look for new process starts that originate from the Outlook PID.</span></span>

- <span data-ttu-id="97394-146">사용자 지정 양식 위험 노출 표시기:</span><span class="sxs-lookup"><span data-stu-id="97394-146">Indicators of the Custom forms compromise:</span></span>

  - <span data-ttu-id="97394-147">사용자 지정 양식이 자신의 메시지 클래스로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="97394-147">Custom form present saved as their own message class.</span></span>

  - <span data-ttu-id="97394-148">메시지 클래스가 실행 코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-148">Message class contains executable code.</span></span>

  - <span data-ttu-id="97394-149">보통 개인 양식 라이브러리 또는 받은 편지함 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="97394-149">Usually stored in Personal Forms Library or Inbox folders.</span></span>

  - <span data-ttu-id="97394-150">양식의 이름은 IPM.Note.[사용자 지정 이름]으로 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-150">Form is named IPM.Note.[custom name].</span></span>

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a><span data-ttu-id="97394-151">이 공격의 신호를 찾고 확인하는 단계</span><span class="sxs-lookup"><span data-stu-id="97394-151">Steps for finding signs of this attack and confirming it</span></span>

<span data-ttu-id="97394-152">다음의 두 가지 방법 중 하나를 사용하여 공격을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-152">You can use either of these two methods to confirm the attack:</span></span>

- <span data-ttu-id="97394-153">Outlook 클라이언트를 사용하여 각 사서함에 대한 규칙과 양식을 수동으로 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-153">Manually examine the rules and forms for each mailbox using the Outlook client.</span></span> <span data-ttu-id="97394-154">이 방법은 철저하지만 한번에 한 명의 사서함 사용자만 검사할 수 있어 검사할 사용자가 많은 경우에는 막대한 시간이 소요됩니다.</span><span class="sxs-lookup"><span data-stu-id="97394-154">This method is thorough, but you can only check mailbox user at a time which can be very time consuming if you have many users to check.</span></span> <span data-ttu-id="97394-155">또한 검사를 실행하는 컴퓨터를 침해할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-155">It can also result in a breach of the computer that you are running the check from.</span></span>

- <span data-ttu-id="97394-156">[Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell 스크립트를 사용하여 테넌트의 모든 사용자에 대한 모든 메일 전달 규칙과 사용자 지정 양식을 자동으로 덤프합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-156">Use the [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script to automatically dump all the mail forwarding rules and custom forms for all the users in your tenancy.</span></span> <span data-ttu-id="97394-157">이 방법은 최소한의 오버 헤드를 사용하는 가장 빠르고 안전한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="97394-157">This is the fastest and safest method with the least amount of overhead.</span></span>

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a><span data-ttu-id="97394-158">Outlook 클라이언트를 사용하여 규칙의 공격을 확인</span><span class="sxs-lookup"><span data-stu-id="97394-158">Confirm the Rules Attack Using the Outlook client</span></span>

1. <span data-ttu-id="97394-159">사용자로 사용자 Outlook 클라이언트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="97394-159">Open the users Outlook client as the user.</span></span> <span data-ttu-id="97394-160">사용자는 사서함에 대한 규칙을 확인하는 데 도움이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-160">The user may need your help in examining the rules on their mailbox.</span></span>

2. <span data-ttu-id="97394-161">Outlook에서 규칙 인터페이스를 여는 방법에 대한 절차는 [규칙을 사용하여 전자 메일 메시지 관리](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97394-161">Refer to [Manage email messages by using rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) article for the procedures on how to open the rules interface in Outlook.</span></span>

3. <span data-ttu-id="97394-162">사용자가 만들지 않은 규칙 또는 의심스러운 이름을 사용하여 예기치 않은 규칙이나 규칙을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-162">Look for rules that the user did not create, or any unexpected rules or rules with suspicious names.</span></span>

4. <span data-ttu-id="97394-163">규칙 설명에서 응용 프로그램을 시작하거나 .EXE, .ZIP을 참조하거나 URL을 실행하는 규칙 작업을 찾아봅니다.</span><span class="sxs-lookup"><span data-stu-id="97394-163">Look in the rule description for rule actions that start and application or refer to an .EXE, .ZIP file or to launching a URL.</span></span>

5. <span data-ttu-id="97394-164">Outlook 프로세스 ID를 사용하여 시작하는 새 프로세스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-164">Look for any new processes that start using the Outlook process ID.</span></span> <span data-ttu-id="97394-165">[프로세스 ID 찾기](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-165">Refer to [Find the Process ID](https://docs.microsoft.com/windows-hardware/drivers/debugger/finding-the-process-id).</span></span>

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a><span data-ttu-id="97394-166">Outlook 클라이언트를 사용하여 양식 공격을 확인하는 단계</span><span class="sxs-lookup"><span data-stu-id="97394-166">Steps to confirm the Forms attack using the Outlook client</span></span>

1. <span data-ttu-id="97394-167">사용자로 사용자 Outlook 클라이언트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="97394-167">Open the user Outlook client as the user.</span></span>

2. <span data-ttu-id="97394-168">사용자 버전의 Outlook에서의 [개발자 탭을 표시](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45)에 나와 있는 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="97394-168">Follow the steps in, [Show the Developer tab](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) for the users version of Outlook.</span></span>

3. <span data-ttu-id="97394-169">Outlook에서 현재 표시되는 개발자 탭을 열고 **양식 디자인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-169">Open the now visible developer tab in Outlook and click **design a form**.</span></span>

4. <span data-ttu-id="97394-170">**찾기** 목록에서 **받은 편지함** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-170">Select the **Inbox** from the **Look In** list.</span></span> <span data-ttu-id="97394-171">사용자 지정 양식을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-171">Look for any custom forms.</span></span> <span data-ttu-id="97394-172">사용자 지정 양식은 거의 드물지만 사용자 지정 양식이 있는 경우에도 더 깊이 있게 확인할 가치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-172">Custom forms are rare enough that if you have any custom forms at all, it is worth a deeper look.</span></span>

5. <span data-ttu-id="97394-173">특히 숨김으로 표시된 사용자 지정 양식을 조사 합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-173">Investigate any custom forms, especially those marked as hidden.</span></span>

6. <span data-ttu-id="97394-174">사용자 지정 양ㅇ식을 열고 **양식** 그룹에서 **코드 보기** 를 클릭하여 양식이 로드될 때 어떤 작업이 실행되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-174">Open any custom forms and in the **Form** group click **View Code** to see what runs when the form is loaded.</span></span>

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a><span data-ttu-id="97394-175">PowerShell을 사용하여 규칙과 양식 공격을 확인 하는 단계</span><span class="sxs-lookup"><span data-stu-id="97394-175">Steps to confirm the Rules and Forms attack using PowerShell</span></span>

<span data-ttu-id="97394-176">규칙 또는 사용자 지정 양식 공격을 확인하는 가장 간단한 방법은 [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell 스크립트를 실행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="97394-176">The simplest way to verify a rules or custom forms attack is to run the [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script.</span></span> <span data-ttu-id="97394-177">이 스크립트는 테넌트의 모든 사서함에 연결하 고 모든 규칙과 양식을 두 개의 .csv 파일로 덤프합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-177">This script connects to every mailbox in your tenant and dumps all the rules and forms into two .csv files.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="97394-178">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="97394-178">Pre-requisites</span></span>

<span data-ttu-id="97394-179">스크립트가 테넌트의 모든 사서함에 연결하여 규칙과 양식을 읽기 때문에 스크립트를 실행하려면 전역 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-179">You will need to have a global administrator rights to run the script because the script connects to every mailbox in the tenancy to read the rules and forms.</span></span>

1. <span data-ttu-id="97394-180">로컬 관리자 권한으로 스크립트를 실행할 컴퓨터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-180">Sign in to the machine that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="97394-181">GitHub에서 Get-AllTenantRulesAndForms.ps1 스크립트를 실행할 폴더로 다운로드하거나 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-181">Download or copy the Get-AllTenantRulesAndForms.ps1 script from GitHub to a folder from which you will run it.</span></span> <span data-ttu-id="97394-182">이 스크립트는 이 폴더 MailboxFormsExport-yyyy-mm-dd.csv 및 MailboxRulesExport-yyyy-mm-dd.csv에 2개의 날짜 스탬프가 찍힌 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="97394-182">The script will create two date stamped files to this folder, MailboxFormsExport-yyyy-mm-dd.csv, and MailboxRulesExport-yyyy-mm-dd.csv.</span></span>

3. <span data-ttu-id="97394-183">PowerShell 인스턴스를 관리자로 열고 스크립트를 저장한 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="97394-183">Open a PowerShell instance as an administrator and open the folder you saved the script to.</span></span>

4. <span data-ttu-id="97394-184">`.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1과 같이이 PowerShell 명령줄을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-184">Run this PowerShell command line as follows `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1</span></span>

#### <a name="interpreting-the-output"></a><span data-ttu-id="97394-185">결과 해석</span><span class="sxs-lookup"><span data-stu-id="97394-185">Interpreting the output</span></span>

- <span data-ttu-id="97394-186">**MailboxRulesExport *-yyyy-mm-dd*.csv**: 응용 프로그램 또는 실행 파일이 포함된 작동 조건에 대한 규칙(행 당 하나씩)을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-186">**MailboxRulesExport-*yyyy-mm-dd*.csv**: Examine the rules (one per row) for action conditions that include applications or executables:</span></span>

  - <span data-ttu-id="97394-187">**ActionType(A열)**: "ID_ACTION_CUSTOM" 값이 표시되는 경우 이 규칙은 악의가 있을 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="97394-187">**ActionType (column A)**: If you see the value "ID_ACTION_CUSTOM", the rule is likely malicious.</span></span>

  - <span data-ttu-id="97394-188">**IsPotentiallyMalicious(D열)**:이 값이 "TRUE" 인 경우 이 규칙은 악의가 있을 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="97394-188">**IsPotentiallyMalicious (column D)**: If this value is "TRUE", the rule is likely malicious.</span></span>

  - <span data-ttu-id="97394-189">**ActionCommand(G열)**: 응용 프로그램이 나 확장명이 .exe, .zip인 파일 또는 있지 않아야 할 URL을 참조하는 항목이 열거되는 경우 이 규칙은 악의가 있을 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="97394-189">**ActionCommand (column G)**: If this lists an application or any file with a .exe, .zip extension or an entry that refers to a URL, that is not supposed to be there, the rule is likely malicious.</span></span>

- <span data-ttu-id="97394-190">**MailboxFormsExport *-yyyy-mm-dd*.csv**: 일반적으로 사용자 지정 양식을 사용하는 경우는 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-190">**MailboxFormsExport-*yyyy-mm-dd*.csv**: In general, the use of custom forms is very rare.</span></span> <span data-ttu-id="97394-191">이 통합 문서에서 양식을 찾은 경우 해당 사용자의 사서함을 열고 양식 자체를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-191">If you find any in this workbook, you open that user's mailbox and examine the form itself.</span></span> <span data-ttu-id="97394-192">조직에서 의도적으로 이를 추가하지 않은 경우 악의가 있을 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="97394-192">If your organization did not put it there intentionally, it is likely malicious.</span></span>

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a><span data-ttu-id="97394-193">Outlook 규칙과 양식 공격을 중지하고 재구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="97394-193">How to stop and remediate the Outlook Rules and Forms attack</span></span>

<span data-ttu-id="97394-194">이러한 공격에 대한 증거를 발견한 경우에는 재구성이 간단하며 사서함에서 규칙이나 양식을 삭제하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97394-194">If you find any evidence of either of these attacks, remediation is simple, just delete the rule or form from the mailbox.</span></span> <span data-ttu-id="97394-195">Outlook 클라이언트에서 이 작업을 수행하거나 원격 PowerShell을 사용하여 규칙을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-195">You can do this with the Outlook client or using remote PowerShell to remove rules.</span></span>

### <a name="using-outlook"></a><span data-ttu-id="97394-196">Outlook 사용</span><span class="sxs-lookup"><span data-stu-id="97394-196">Using Outlook</span></span>

1. <span data-ttu-id="97394-197">사용자가 Outlook에서 사용한 모든 장치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-197">Identify all the devices that the user has used with Outlook.</span></span> <span data-ttu-id="97394-198">이들 장치 모두에서 잠정 맬웨어를 청소해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-198">They will all need to be cleaned of potential malware.</span></span> <span data-ttu-id="97394-199">모든 장치를 청소할 때 까지는 사용자가 로그온 하고 전자 메일을 사용하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-199">Do not allow the user to sign on and use email until all the devices are cleaned.</span></span>

2. <span data-ttu-id="97394-200">각 장치에 대한 [규칙 삭제](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f)에 있는 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="97394-200">Follow the steps in [Delete a rule](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) for each device.</span></span>

3. <span data-ttu-id="97394-201">다른 맬웨어의 존재 여부가 확실하지 않은 경우 장치의 모든 소프트웨어를 포맷하고 다시 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-201">If you are unsure about the presence of other malware, you can format and re-install all the software on the device.</span></span> <span data-ttu-id="97394-202">모바일 장치의 경우 제조업체의 단계에 따라 장치를 출하 이미지로 재설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-202">For mobile devices you can follow the manufacturers steps to reset the device to the factory image.</span></span>

4. <span data-ttu-id="97394-203">최신 버전의 Outlook을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-203">Install the most up-to-date versions of Outlook.</span></span> <span data-ttu-id="97394-204">최신 버전의 Outlook은 기본적으로 이 두 가지 유형의 공격을 차단한다는 사실을 기억하세요.</span><span class="sxs-lookup"><span data-stu-id="97394-204">Remember that the current version of Outlook blocks both types of this attack by default.</span></span>

5. <span data-ttu-id="97394-205">사서함의 모든 오프라인 복사본이 제거된 후 사용자의 암호를 다시 설정하고(고품질의 복사본 사용) MFA를 아직 사용하도록 설정하지 않은 경우 사용자에 대해 다단계 인증을 설치하는 단계를 수행합니다. [](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="97394-205">Once all offline copies of the mailbox have been removed, reset the user's password (use a high-quality one) and follow the steps in [Setup multi-factor authentication for users](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) if MFA has not already been enabled.</span></span> <span data-ttu-id="97394-206">이렇게 하면 사용자의 자격 증명이 다른 수단(예: 피싱 또는 암호 재사용)을 통해 노출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-206">This ensures that the user's credentials are not exposed via other means (such as phishing or password re-use).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="97394-207">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="97394-207">Using PowerShell</span></span>

<span data-ttu-id="97394-208">위험한 규칙을 제거하거나 해제하는 데 사용할 수 있는 두 개의 원격 PowerShell cmdlet이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-208">There are two remote PowerShell cmdlets you can use to remove or disable dangerous rules.</span></span> <span data-ttu-id="97394-209">다음의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="97394-209">Just follow the steps.</span></span>

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a><span data-ttu-id="97394-210">Exchange 서버에 있는 사서함에 대한 단계</span><span class="sxs-lookup"><span data-stu-id="97394-210">Steps for mailboxes that are on an Exchange server</span></span>

1. <span data-ttu-id="97394-211">원격 PowerShell을 사용하여 Exchange 서버에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-211">Connect to the Exchange server using remote PowerShell.</span></span> <span data-ttu-id="97394-212">[원격 PowerShell을 사용하여 Exchange 서버에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)에 있는 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="97394-212">Follow the steps in [Connect to Exchange servers using remote PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="97394-213">사서함의 단일 규칙, 여러 규칙 또는 모든 규칙을 완전히 제거하려면 [InboxRule 제거](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-213">If you want to completely remove a single rule, multiple rules, or all rules from a mailbox use the [Remove-InboxRule](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) cmdlet.</span></span>

3. <span data-ttu-id="97394-214">추가 조사를 위해 규칙과 해당 콘텐츠를 보존하려면 [InboxRule 비활성화](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-214">If you want to retain the rule and its contents for further investigation use the [Disable-InboxRule](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) cmdlet.</span></span>

#### <a name="steps-for-mailboxes-in-exchange-online"></a><span data-ttu-id="97394-215">Exchange Online의 사서함에 대한 단계</span><span class="sxs-lookup"><span data-stu-id="97394-215">Steps for mailboxes in Exchange Online</span></span>

1. <span data-ttu-id="97394-216">[PowerShell을 사용하여 Exchange Online에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)에 있는 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="97394-216">Follow the steps in [Connect to Exchange Online using PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="97394-217">사서함의 단일 규칙, 여러 규칙 또는 모든 규칙을 완전히 제거하려면 [받은 편지함 제거 규칙](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-217">If you want to completely remove a single rule, multiple rules, or all rules from a mailbox use the [Remove-Inbox Rule](https://docs.microsoft.com/powershell/module/exchange/Remove-InboxRule) cmdlet.</span></span>

3. <span data-ttu-id="97394-218">추가 조사를 위해 규칙과 해당 콘텐츠를 보존하려면 [InboxRule 비활성화](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-218">If you want to retain the rule and its contents for further investigation use the [Disable-InboxRule](https://docs.microsoft.com/powershell/module/exchange/disable-inboxrule) cmdlet.</span></span>

## <a name="how-to-minimize-future-attacks"></a><span data-ttu-id="97394-219">미래의 공격을 최소화하는 방법</span><span class="sxs-lookup"><span data-stu-id="97394-219">How to minimize future attacks</span></span>

### <a name="first-protect-your-accounts"></a><span data-ttu-id="97394-220">첫 번째: 계정 보호</span><span class="sxs-lookup"><span data-stu-id="97394-220">First: protect your accounts</span></span>

<span data-ttu-id="97394-221">사용자 계정 중 하나를 도난 혹은 침해를 받은 경우에만 공격자가 이 규칙과 양식을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-221">The Rules and Forms exploits are only used by an attacker after they have stolen or breached one of your user's accounts.</span></span> <span data-ttu-id="97394-222">따라서 조직에서 이러한 악용을 방지하는 첫 번째 단계는 사용자 계정을 적극적으로 보호하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="97394-222">So, your first step to preventing the use of these exploits against your organization is to aggressively protect your user accounts.</span></span> <span data-ttu-id="97394-223">계정을 침해하는 가장 일반적인 방법 중 일부는 피싱 또는 [암호 스프레이](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) 공격을 통해 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-223">Some of the most common ways that accounts are breached are through phishing or [password spraying](https://www.dabcc.com/microsoft-defending-against-password-spray-attacks/) attacks.</span></span>

<span data-ttu-id="97394-224">사용자 계정 및 특히 관리자 계정을 보호하는 가장 좋은 방법은 사용자에 대해 다단계 인증을 [설정하는 것입니다.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="97394-224">The best way to protect your user accounts, and especially your administrator accounts, is to [set up multi-factor authentication for users](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span> <span data-ttu-id="97394-225">사용자는 또한:</span><span class="sxs-lookup"><span data-stu-id="97394-225">You should also:</span></span>

- <span data-ttu-id="97394-226">사용자 계정이 [액세스되고 사용되는](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports) 방식을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-226">Monitor how your user accounts are [accessed and used](https://docs.microsoft.com/azure/active-directory/active-directory-view-access-usage-reports).</span></span> <span data-ttu-id="97394-227">초기 침해를 방지하지 못할 수 있지만 침해의 기간과 영향은 더 일찍 발견하여 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-227">You may not prevent the initial breach, but you will shorten the duration and the impact of the breach by detecting it sooner.</span></span> <span data-ttu-id="97394-228">[Office 365 클라우드 앱 보안 정책](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)을 사용 하여 계정을 모니터링하고 비정상적 활동에 대 한 알림을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-228">You can use these [Office 365 Cloud App Security policies](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) to monitor you accounts and alert on unusual activity:</span></span>

  - <span data-ttu-id="97394-229">**로그인 시도의 수차례 실패**: 이 정책은 침해의 시도를 나타낼 수 있는 학습한 기준을 고려하여 단일 세션에서 수차례 로그인 활동에 실패하는 경우 사용자 환경을 프로파일링하고 알림을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-229">**Multiple failed login attempts**: This policy profiles your environment and triggers alerts when users perform multiple failed login activities in a single session with respect to the learned baseline, which could indicate an attempted breach.</span></span>

  - <span data-ttu-id="97394-230">**불가능한 이동**: 이 정책은 사용자 환경을 프로파일링하고 두 위치 사이의 예상 이동 시간 보다 짧은 기간에 여러 위치에 있는 같은 사용자의 다른 위치에서의 활동을 탐지하는 경우 알림을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-230">**Impossible travel**: This policy profiles your environment and triggers alerts when activities are detected from the same user in different locations within a time period that is shorter than the expected travel time between the two locations.</span></span> <span data-ttu-id="97394-231">이는 다른 사용자가 동일한 자격 증명을 사용 하고 있음을 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-231">This could indicate that a different user is using the same credentials.</span></span> <span data-ttu-id="97394-232">이 비정상 동작의 탐지는 새 사용자의 활동 패턴을 학습하는 동안 초기 7일의 학습 기간을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-232">Detecting this anomalous behavior necessitates an initial learning period of seven days during which it learns a new user's activity pattern.</span></span>

  - <span data-ttu-id="97394-233">**비정상적 가장 활동(사용자)**: 이 정책은 침해의 시도를 나타낼 수 있는 학습한 기준을 고려하여 단일 세션에서 수차례 가장 활동을 수행하는 경우 사용자 환경을 프로파일링하고 알림을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-233">**Unusual impersonated activity (by user)**: This policy profiles your environment and triggers alerts when users perform multiple impersonated activities in a single session with respect to the baseline learned, which could indicate an attempted breach.</span></span>

- <span data-ttu-id="97394-234">[Office 365 보안 점수](https://securescore.office.com/)와 같은 도구를 활용 하여 계정 보안의 구성과 동작을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-234">Leverage a tool like [Office 365 Secure Score](https://securescore.office.com/) to manage account security configurations and behaviors.</span></span>

### <a name="second-keep-your-outlook-clients-current"></a><span data-ttu-id="97394-235">두 번째: Outlook 클라이언트를 최신 상태로 유지</span><span class="sxs-lookup"><span data-stu-id="97394-235">Second: Keep your Outlook clients current</span></span>

<span data-ttu-id="97394-236">완벽하게 업데이트되고 패치가 적용된 Outlook 2013과 2016은 "응용 프로그램 시작" 규칙/양식 작업은 기본적으로 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-236">Fully-updated and patched versions of Outlook 2013, and 2016 disable the "Start Application" rule/form action by default.</span></span> <span data-ttu-id="97394-237">이렇게 하면 공격자가 계정을 침해하더라도 규칙과 양식 작업이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="97394-237">This will ensure that, even if an attacker breaches the account, the rule and form actions will be blocked.</span></span> <span data-ttu-id="97394-238">[Office 업데이트 설치](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)단계를 따라 최신 업데이트 및 보안 패치를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-238">You can install the latest updates and security patches by following the steps in [Install Office updates](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5).</span></span>

<span data-ttu-id="97394-239">다음은 Outlook 2013 및 2016 클라이언트용 패치 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="97394-239">Here are the patch versions for your Outlook 2013 and 2016 clients:</span></span>

- <span data-ttu-id="97394-240">**Outlook 2016**: 16.0.4534.1001 이상.</span><span class="sxs-lookup"><span data-stu-id="97394-240">**Outlook 2016**: 16.0.4534.1001 or greater.</span></span>

- <span data-ttu-id="97394-241">**Outlook 2013**: 15.0.4937.1000 이상.</span><span class="sxs-lookup"><span data-stu-id="97394-241">**Outlook 2013**: 15.0.4937.1000 or greater.</span></span>

<span data-ttu-id="97394-242">개별 보안 패치에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97394-242">For more information on the individual security patches, see:</span></span>

- [<span data-ttu-id="97394-243">Outlook 2016 보안 패치</span><span class="sxs-lookup"><span data-stu-id="97394-243">Outlook 2016 Security Patch</span></span>](https://support.microsoft.com/help/3191883)

- [<span data-ttu-id="97394-244">Outlook 2013 보안 패치</span><span class="sxs-lookup"><span data-stu-id="97394-244">Outlook 2013 Security Patch</span></span>](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a><span data-ttu-id="97394-245">세 번째: Outlook 클라이언트 모니터링</span><span class="sxs-lookup"><span data-stu-id="97394-245">Third: Monitor your Outlook clients</span></span>

<span data-ttu-id="97394-246">패치 및 업데이트가 설치되어 있더라도 공격자가 로컬 컴퓨터 구성을 변경하여 "응용 프로그램 시작" 동작을 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-246">Note that even with the patches and updates installed, it is possible for an attacker to change the local machine configuration to re-enable the "Start Application" behavior.</span></span> <span data-ttu-id="97394-247">[고급 그룹 정책 관리](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/)를 사용하여 클라이언트에서 로컬 컴퓨터 정책을 모니터링하고 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-247">You can use [Advanced Group Policy Management](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm/) to monitor and enforce local machine policies on your clients.</span></span>

<span data-ttu-id="97394-248">[64 비트 버전의 Windows를 사용하여 시스템 레지스트리를 보는 방법](https://support.microsoft.com/help/305097)의 정보를 사용하여 "시작 응용 프로그램"이 레지스트리에 오버라이드를 통해 다시 사용하도록 설정되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-248">You can to see if "Start Application" has been re-enabled through an override in the registry by using the information in [How to view the system registry by using 64-bit versions of Windows](https://support.microsoft.com/help/305097).</span></span> <span data-ttu-id="97394-249">다음의 하위 키를 확인합니다:</span><span class="sxs-lookup"><span data-stu-id="97394-249">Check these subkeys:</span></span>

- <span data-ttu-id="97394-250">**Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`</span><span class="sxs-lookup"><span data-stu-id="97394-250">**Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`</span></span>

- <span data-ttu-id="97394-251">**Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`</span><span class="sxs-lookup"><span data-stu-id="97394-251">**Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`</span></span>

<span data-ttu-id="97394-252">EnableUnsafeClientMailRules 키를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-252">Look for the key EnableUnsafeClientMailRules.</span></span> <span data-ttu-id="97394-253">찾았고 1로 설정되어 있으면 Outlook 보안 패치가 오버라이드되었고 컴퓨터가 양식/규칙 공격에 취약합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-253">If it is there and is set to 1, the Outlook security patch has been overridden and the computer is vulnerable to the Form/Rules attack.</span></span> <span data-ttu-id="97394-254">값이 0 이면 "응용 프로그램 시작" 작업을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-254">If the value is 0, the "Start Application" action is disabled.</span></span> <span data-ttu-id="97394-255">업데이트되고 패치가 적용된 버전의 Outlook이 설치되었고 이 레지스트리 키가 없는 경우에는 시스템이 이러한 공격에 취약하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-255">If the updated and patched version of Outlook is installed and this registry key is not present, then a system is not vulnerable to these attacks.</span></span>

<span data-ttu-id="97394-256">온-프레미스 Exchange 설치를 사용하는 고객은 사용 가능한 패치가 없는 이전 버전의 Outlook을 차단하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-256">Customers with on-premises Exchange installations should consider blocking older versions of Outlook that do not have patches available.</span></span> <span data-ttu-id="97394-257">이 프로세스에 대한 자세한 내용은 [Outlook 클라이언트 차단 구성](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97394-257">Details on this process can be found in the article [Configure Outlook client blocking](https://docs.microsoft.com/exchange/configure-outlook-client-blocking-exchange-2013-help).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="97394-258">사이버 보안 프로그램과 같은 Microsoft 365 보안</span><span class="sxs-lookup"><span data-stu-id="97394-258">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="97394-259">Microsoft 365 구독에는 데이터 및 사용자를 보호하는 데 사용할 수 있는 강력한 보안 기능이 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="97394-259">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="97394-260">[Microsoft 365 보안 로드맵 - 최초 30일, 90일 및 그 이후의 최우선 순위](security-roadmap.md)를 사용하여 Microsoft에서 권장하는 Microsoft 365 테넌트 보안을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-260">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="97394-261">처음 30일 이내에 수행 할 작업</span><span class="sxs-lookup"><span data-stu-id="97394-261">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="97394-262">이러한 작업들은 즉각적인 영향을 미치며 사용자에게 영향을 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="97394-262">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="97394-263">90일 이내에 수행해야 할 작업</span><span class="sxs-lookup"><span data-stu-id="97394-263">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="97394-264">이러한 작업들은 계획하고 구현하는 데 다소 시간이 걸리지만 보안 태세를 갖추는 데 큰 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="97394-264">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="97394-265">90일 초과</span><span class="sxs-lookup"><span data-stu-id="97394-265">Beyond 90 days.</span></span> <span data-ttu-id="97394-266">이러한 향상된 기능은 처음 90일간의 작업에서 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="97394-266">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="97394-267">참고 항목:</span><span class="sxs-lookup"><span data-stu-id="97394-267">See also:</span></span>

- <span data-ttu-id="97394-268">규칙 벡터에 대한 SilentBreak 보안 게시물 [악의적 Outlook 규칙](https://silentbreaksecurity.com/malicious-outlook-rules/)은 Outlook 규칙에 대한 자세한 검토를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-268">[Malicious Outlook Rules](https://silentbreaksecurity.com/malicious-outlook-rules/) by SilentBreak Security Post about Rules Vector provides a detailed review of how the Outlook Rules.</span></span>

- <span data-ttu-id="97394-269">Mailrule Pwnage에 대한 Sensepost 블로그 [HTTP 및 Mailrule Pwnage를 통한 MAPI](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/)는 Outlook 규칙을 통해 사서함을 이용하게 해주는 Ruler라는 도구에 대해 설명을 합니다.</span><span class="sxs-lookup"><span data-stu-id="97394-269">[MAPI over HTTP and Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) on the Sensepost blog about Mailrule Pwnage discusses a tool called Ruler that lets you exploit mailboxes through Outlook rules.</span></span>

- <span data-ttu-id="97394-270">양식 위협 벡터에 대한 Sensepost 블로그의 [Outlook 양식 및 셸](https://sensepost.com/blog/2017/outlook-forms-and-shells/)</span><span class="sxs-lookup"><span data-stu-id="97394-270">[Outlook forms and shells](https://sensepost.com/blog/2017/outlook-forms-and-shells/) on the Sensepost blog about Forms Threat Vector.</span></span>

- [<span data-ttu-id="97394-271">Ruler 코드 베이스</span><span class="sxs-lookup"><span data-stu-id="97394-271">Ruler Codebase</span></span>](https://github.com/sensepost/ruler)

- [<span data-ttu-id="97394-272">Ruler 위험 노출 표시기</span><span class="sxs-lookup"><span data-stu-id="97394-272">Ruler Indicators of Compromise</span></span>](https://github.com/sensepost/notruler/blob/master/iocs.md)
