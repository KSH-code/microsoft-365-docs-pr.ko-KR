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
ms.openlocfilehash: 0846051b65b34ec26358f87bb4ca49302573e6e7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072572"
---
# <a name="detect-and-remediate-outlook-rules-and-custom-forms-injections-attacks"></a><span data-ttu-id="8efc0-103">Outlook 규칙 및 사용자 지정 양식 주입 공격 감지 및 재구성</span><span class="sxs-lookup"><span data-stu-id="8efc0-103">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="8efc0-104">**요약** Office 365에서 Outlook 규칙 및 사용자 지정 양식 주입 공격을 인지하고 재구성하는 방법 알아보기</span><span class="sxs-lookup"><span data-stu-id="8efc0-104">**Summary** Learn how to recognize and remediate the Outlook rules and custom Forms injections attacks in Office 365.</span></span>

## <a name="what-is-the-outlook-rules-and-custom-forms-injection-attack"></a><span data-ttu-id="8efc0-105">Outlook 규칙과 사용자 지정 양식 주입 공격은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="8efc0-105">What is the Outlook Rules and Custom Forms injection attack?</span></span>

<span data-ttu-id="8efc0-106">공격자가 조직에 대한 액세스 권한을 얻게 된 후 발견된 후 계속 유지하거나 다시 들어오기 위한 발판을 설정하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-106">After an attacker gains access to your organization, they'll try to establish a foothold to stay in or get back in after they've been discovered.</span></span> <span data-ttu-id="8efc0-107">이 활동을 *지속성 메커니즘 설정이라고 합니다.*</span><span class="sxs-lookup"><span data-stu-id="8efc0-107">This activity is called *establishing a persistence mechanism*.</span></span> <span data-ttu-id="8efc0-108">공격자가 Outlook을 사용하여 지속성 메커니즘을 설정하는 방법에는 다음 두 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-108">There are two ways that an attacker can use Outlook to establish a persistence mechanism:</span></span>

- <span data-ttu-id="8efc0-109">Outlook 규칙을 악용하여</span><span class="sxs-lookup"><span data-stu-id="8efc0-109">By exploiting Outlook rules.</span></span>
- <span data-ttu-id="8efc0-110">Outlook에 사용자 지정 양식을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-110">By injecting custom forms into Outlook.</span></span>

<span data-ttu-id="8efc0-111">Outlook을 다시 설치하거나 영향을 받는 사용자에게 새 컴퓨터를 제공하면 도움이되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-111">Reinstalling Outlook, or even giving the affected person a new computer won't help.</span></span> <span data-ttu-id="8efc0-112">Outlook을 처음 설치할 때 사서함에 연결하면 모든 규칙과 양식이 클라우드에서 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-112">When the fresh installation of Outlook connects to the mailbox, all rules and forms are synchronized from the cloud.</span></span> <span data-ttu-id="8efc0-113">규칙 또는 양식은 일반적으로 원격 코드를 실행하고 로컬 컴퓨터에 맬웨어를 설치하도록 디자인됩니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-113">The rules or forms are typically designed to run remote code and install malware on the local machine.</span></span> <span data-ttu-id="8efc0-114">맬웨어는 자격 증명을 훔치거나 다른 악성 활동을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-114">The malware steals credentials or performs other illicit activity.</span></span>

<span data-ttu-id="8efc0-115">다행히도 Outlook 클라이언트가 최신 버전으로 패치된 경우 현재 Outlook 클라이언트 기본값이 두 메커니즘을 모두 차단하기 때문에 위협에 취약하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-115">The good news is: if you keep your Outlook clients patched to the latest version, you aren't vulnerable to the threat as current Outlook client defaults block both mechanisms.</span></span>

<span data-ttu-id="8efc0-116">이 공격은 일반적으로 다음의 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-116">The attacks typically follow these patterns:</span></span>

<span data-ttu-id="8efc0-117">**규칙 활용**:</span><span class="sxs-lookup"><span data-stu-id="8efc0-117">**The Rules Exploit**:</span></span>

1. <span data-ttu-id="8efc0-118">공격자는 사용자의 자격 증명을 도용합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-118">The attacker steals a user's credentials.</span></span>

2. <span data-ttu-id="8efc0-119">공격자는 해당 사용자의 Exchange 사서함(Exchange Online 또는 사내 Exchange)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-119">The attacker signs in to that user's Exchange mailbox (Exchange Online or on-premises Exchange).</span></span>

3. <span data-ttu-id="8efc0-120">공격자는 사서함에 전달 받은 편지함 규칙을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-120">The attacker creates a forwarding Inbox rule in the mailbox.</span></span> <span data-ttu-id="8efc0-121">전달 규칙은 사서함이 규칙의 조건과 일치하는 공격자로부터 특정 메시지를 받을 때 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-121">The forwarding rule is triggered when the mailbox receives a specific message from the attacker that matches the conditions of the rule.</span></span> <span data-ttu-id="8efc0-122">규칙 조건과 메시지 형식은 서로에 맞게 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-122">The rule conditions and message format are tailor-made for each other.</span></span>

4. <span data-ttu-id="8efc0-123">공격자는 손상된 사서함으로 트리거 전자 메일을 전송합니다. 이 전자 메일은 여전히 사용자가 예상하지 않는 사용자에 의해 정상으로 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-123">The attacker sends the trigger email to the compromised mailbox, which is still being used as normal by the unsuspecting user.</span></span>

5. <span data-ttu-id="8efc0-124">사서함이 규칙 조건과 일치하는 메시지를 받으면 규칙 동작이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-124">When the mailbox receives a message that matches the conditions of rule, the action of the rule is applied.</span></span> <span data-ttu-id="8efc0-125">일반적으로는 원격(WebDAV) 서버에서 응용 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-125">Typically, the rule action is to launch an application on a remote (WebDAV) server.</span></span>

6. <span data-ttu-id="8efc0-126">일반적으로 응용 프로그램은 사용자의 컴퓨터에 맬웨어를 설치합니다(예: [PowerShell 원시).](https://www.powershellempire.com/)</span><span class="sxs-lookup"><span data-stu-id="8efc0-126">Typically, the application installs malware on the user's machine (for example, [PowerShell Empire](https://www.powershellempire.com/)).</span></span>

7. <span data-ttu-id="8efc0-127">맬웨어를 사용하면 공격자가 로컬 컴퓨터의 사용자 이름과 암호 또는 기타 자격 증명을 훔치거나 다시 훔쳐 다른 악의적인 활동을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-127">The malware allows the attacker to steal (or steal again) the user's username and password or other credentials from local machine and perform other malicious activities.</span></span>

<span data-ttu-id="8efc0-128">**양식 활용**:</span><span class="sxs-lookup"><span data-stu-id="8efc0-128">**The Forms Exploit**:</span></span>

1. <span data-ttu-id="8efc0-129">공격자는 사용자의 자격 증명을 도용합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-129">The attacker steals a user's credentials.</span></span>

2. <span data-ttu-id="8efc0-130">공격자는 해당 사용자의 Exchange 사서함(Exchange Online 또는 사내 Exchange)에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-130">The attacker signs in to that user's Exchange mailbox (Exchange Online or on-premises Exchange).</span></span>

3. <span data-ttu-id="8efc0-131">공격자는 사용자 사서함에 사용자 지정 메일 양식 서식 파일을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-131">The attacker inserts a custom mail form template into the user's mailbox.</span></span> <span data-ttu-id="8efc0-132">사용자 지정 양식은 사서함이 사용자 지정 양식을 로드해야 하는 공격자로부터 특정 메시지를 받을 때 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-132">The custom form is triggered when the mailbox receives a specific message from the attacker that requires the mailbox to load the custom form.</span></span> <span data-ttu-id="8efc0-133">사용자 지정 양식과 메시지 형식은 서로에 맞게 조정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-133">The custom form and the message format are tailor-made for each other.</span></span>

4. <span data-ttu-id="8efc0-134">공격자는 손상된 사서함으로 트리거 전자 메일을 전송합니다. 이 전자 메일은 여전히 사용자가 예상하지 않는 사용자에 의해 정상으로 사용 중입니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-134">The attacker sends the trigger email to the compromised mailbox, which is still being used as normal by the unsuspecting user.</span></span>

5. <span data-ttu-id="8efc0-135">사서함이 메시지를 받으면 사서함은 필요한 양식을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-135">When the mailbox receives the message, the mailbox loads the required form.</span></span> <span data-ttu-id="8efc0-136">양식은 원격(WebDAV) 서버에서 응용 프로그램을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-136">The form launches an application on a remote (WebDAV) server.</span></span>

6. <span data-ttu-id="8efc0-137">일반적으로 응용 프로그램은 사용자의 컴퓨터에 맬웨어를 설치합니다(예: [PowerShell 원시).](https://www.powershellempire.com/)</span><span class="sxs-lookup"><span data-stu-id="8efc0-137">Typically, the application installs malware on the user's machine (for example, [PowerShell Empire](https://www.powershellempire.com/)).</span></span>

7. <span data-ttu-id="8efc0-138">맬웨어를 사용하면 공격자가 로컬 컴퓨터의 사용자 이름과 암호 또는 기타 자격 증명을 훔치거나 다시 훔쳐 다른 악의적인 활동을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-138">The malware allows the attacker to steal (or steal again) the user's username and password or other credentials from local machine and perform other malicious activities.</span></span>

## <a name="what-a-rules-and-custom-forms-injection-attack-might-look-like-office-365"></a><span data-ttu-id="8efc0-139">어떠한 규칙 및 사용자 지정 양식 주입 공격이 Office 365와 같아 보일 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="8efc0-139">What a Rules and Custom Forms Injection attack might look like Office 365?</span></span>

<span data-ttu-id="8efc0-140">이러한 지속성 메커니즘은 사용자가 발견할 가능성이 거의 없으며 일부의 경우에 보이지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-140">These persistence mechanisms are unlikely to be noticed by your users and may in some cases even be invisible to them.</span></span> <span data-ttu-id="8efc0-141">이 문서에서는 아래에 나열된 7가지 기호(위험 노출 표시기)를 찾는 방법을 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-141">This article tells you how to look for any of the seven signs (Indicators of Compromise) listed below.</span></span> <span data-ttu-id="8efc0-142">이러한 내용을 발견하면 재구성 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-142">If you find any of these, you need to take remediation steps.</span></span>

- <span data-ttu-id="8efc0-143">**규칙 손상 표시기:**</span><span class="sxs-lookup"><span data-stu-id="8efc0-143">**Indicators of the Rules compromise**:</span></span>
  - <span data-ttu-id="8efc0-144">규칙 작업은 응용 프로그램을 시작하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-144">Rule Action is to start an application.</span></span>
  - <span data-ttu-id="8efc0-145">규칙에서 EXE, ZIP 또는 URL을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-145">Rule References an EXE, ZIP, or URL.</span></span>
  - <span data-ttu-id="8efc0-146">로컬 컴퓨터에서 Outlook PID가 보낸 새 프로세스 시작을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-146">On the local machine, look for new process starts that originate from the Outlook PID.</span></span>

- <span data-ttu-id="8efc0-147">**사용자 지정 양식 손상 표시기:**</span><span class="sxs-lookup"><span data-stu-id="8efc0-147">**Indicators of the Custom forms compromise**:</span></span>
  - <span data-ttu-id="8efc0-148">사용자 지정 양식은 자체 메시지 클래스로 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-148">Custom forms present saved as their own message class.</span></span>
  - <span data-ttu-id="8efc0-149">메시지 클래스가 실행 코드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-149">Message class contains executable code.</span></span>
  - <span data-ttu-id="8efc0-150">일반적으로 악의적인 양식은 개인 양식 라이브러리 또는 받은 편지함 폴더에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-150">Typically, malicious forms are stored in Personal Forms Library or Inbox folders.</span></span>
  - <span data-ttu-id="8efc0-151">양식의 이름은 IPM.Note.[사용자 지정 이름]으로 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-151">Form is named IPM.Note.[custom name].</span></span>

## <a name="steps-for-finding-signs-of-this-attack-and-confirming-it"></a><span data-ttu-id="8efc0-152">이 공격의 신호를 찾고 확인하는 단계</span><span class="sxs-lookup"><span data-stu-id="8efc0-152">Steps for finding signs of this attack and confirming it</span></span>

<span data-ttu-id="8efc0-153">다음 방법 중 하나를 사용하여 공격을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-153">You can use either of the following methods to confirm the attack:</span></span>

- <span data-ttu-id="8efc0-154">Outlook 클라이언트를 사용하여 각 사서함에 대한 규칙과 양식을 수동으로 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-154">Manually examine the rules and forms for each mailbox using the Outlook client.</span></span> <span data-ttu-id="8efc0-155">이 방법은 철저하지만 사서함은 한 번만 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-155">This method is thorough, but you can only check one mailbox at a time.</span></span> <span data-ttu-id="8efc0-156">이 방법은 확인할 사용자가 많고 사용 중이신 컴퓨터를 감염시킬 수도 있는 경우에 매우 시간이 많이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-156">This method can be very time consuming if you have many users to check, and might also infect the computer that you're using.</span></span>

- <span data-ttu-id="8efc0-157">[Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell 스크립트를 사용하여 테넌트의 모든 사용자에 대한 모든 메일 전달 규칙과 사용자 지정 양식을 자동으로 덤프합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-157">Use the [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script to automatically dump all the mail forwarding rules and custom forms for all the users in your tenancy.</span></span> <span data-ttu-id="8efc0-158">이 방법은 최소한의 오버 헤드를 사용하는 가장 빠르고 안전한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-158">This is the fastest and safest method with the least amount of overhead.</span></span>

### <a name="confirm-the-rules-attack-using-the-outlook-client"></a><span data-ttu-id="8efc0-159">Outlook 클라이언트를 사용하여 규칙의 공격을 확인</span><span class="sxs-lookup"><span data-stu-id="8efc0-159">Confirm the Rules Attack Using the Outlook client</span></span>

1. <span data-ttu-id="8efc0-160">사용자로 사용자 Outlook 클라이언트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-160">Open the users Outlook client as the user.</span></span> <span data-ttu-id="8efc0-161">사용자는 사서함에 대한 규칙을 확인하는 데 도움이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-161">The user may need your help in examining the rules on their mailbox.</span></span>

2. <span data-ttu-id="8efc0-162">Outlook에서 규칙 인터페이스를 여는 방법에 대한 절차는 [규칙을 사용하여 전자 메일 메시지 관리](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8efc0-162">Refer to [Manage email messages by using rules](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59) article for the procedures on how to open the rules interface in Outlook.</span></span>

3. <span data-ttu-id="8efc0-163">사용자가 만들지 않은 규칙 또는 의심스러운 이름을 사용하여 예기치 않은 규칙이나 규칙을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-163">Look for rules that the user did not create, or any unexpected rules or rules with suspicious names.</span></span>

4. <span data-ttu-id="8efc0-164">규칙 설명에서 응용 프로그램을 시작하거나 .EXE, .ZIP을 참조하거나 URL을 실행하는 규칙 작업을 찾아봅니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-164">Look in the rule description for rule actions that start and application or refer to an .EXE, .ZIP file or to launching a URL.</span></span>

5. <span data-ttu-id="8efc0-165">Outlook 프로세스 ID를 사용하여 시작하는 새 프로세스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-165">Look for any new processes that start using the Outlook process ID.</span></span> <span data-ttu-id="8efc0-166">[프로세스 ID 찾기](/windows-hardware/drivers/debugger/finding-the-process-id)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-166">Refer to [Find the Process ID](/windows-hardware/drivers/debugger/finding-the-process-id).</span></span>

### <a name="steps-to-confirm-the-forms-attack-using-the-outlook-client"></a><span data-ttu-id="8efc0-167">Outlook 클라이언트를 사용하여 양식 공격을 확인하는 단계</span><span class="sxs-lookup"><span data-stu-id="8efc0-167">Steps to confirm the Forms attack using the Outlook client</span></span>

1. <span data-ttu-id="8efc0-168">사용자로 사용자 Outlook 클라이언트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-168">Open the user Outlook client as the user.</span></span>

2. <span data-ttu-id="8efc0-169">사용자의 Outlook 버전에 대한 개발자 탭 표시의 단계를 따릅니다. [](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45)</span><span class="sxs-lookup"><span data-stu-id="8efc0-169">Follow the steps in, [Show the Developer tab](https://support.microsoft.com/office/e1192344-5e56-4d45-931b-e5fd9bea2d45) for the user's version of Outlook.</span></span>

3. <span data-ttu-id="8efc0-170">Outlook에서 현재 표시되는 개발자 탭을 열고 **양식 디자인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-170">Open the now visible developer tab in Outlook and click **design a form**.</span></span>

4. <span data-ttu-id="8efc0-171">**찾기** 목록에서 **받은 편지함** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-171">Select the **Inbox** from the **Look In** list.</span></span> <span data-ttu-id="8efc0-172">사용자 지정 양식을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-172">Look for any custom forms.</span></span> <span data-ttu-id="8efc0-173">사용자 지정 양식은 거의 드물지만 사용자 지정 양식이 있는 경우에도 더 깊이 있게 확인할 가치가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-173">Custom forms are rare enough that if you have any custom forms at all, it is worth a deeper look.</span></span>

5. <span data-ttu-id="8efc0-174">특히 숨김으로 표시된 사용자 지정 양식을 조사 합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-174">Investigate any custom forms, especially those marked as hidden.</span></span>

6. <span data-ttu-id="8efc0-175">사용자 지정 양ㅇ식을 열고 **양식** 그룹에서 **코드 보기** 를 클릭하여 양식이 로드될 때 어떤 작업이 실행되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-175">Open any custom forms and in the **Form** group click **View Code** to see what runs when the form is loaded.</span></span>

### <a name="steps-to-confirm-the-rules-and-forms-attack-using-powershell"></a><span data-ttu-id="8efc0-176">PowerShell을 사용하여 규칙과 양식 공격을 확인 하는 단계</span><span class="sxs-lookup"><span data-stu-id="8efc0-176">Steps to confirm the Rules and Forms attack using PowerShell</span></span>

<span data-ttu-id="8efc0-177">규칙 또는 사용자 지정 양식 공격을 확인하는 가장 간단한 방법은 [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell 스크립트를 실행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-177">The simplest way to verify a rules or custom forms attack is to run the [Get-AllTenantRulesAndForms.ps1](https://github.com/OfficeDev/O365-InvestigationTooling/blob/master/Get-AllTenantRulesAndForms.ps1) PowerShell script.</span></span> <span data-ttu-id="8efc0-178">이 스크립트는 테넌트의 모든 사서함에 연결하 고 모든 규칙과 양식을 두 개의 .csv 파일로 덤프합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-178">This script connects to every mailbox in your tenant and dumps all the rules and forms into two .csv files.</span></span>

#### <a name="pre-requisites"></a><span data-ttu-id="8efc0-179">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="8efc0-179">Pre-requisites</span></span>

<span data-ttu-id="8efc0-180">스크립트가 테넌트의 모든 사서함에 연결하여 규칙 및 양식을 읽기 때문에 스크립트를 실행하려면 전역 관리자 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-180">You will need to have global administrator rights to run the script because the script connects to every mailbox in the tenancy to read the rules and forms.</span></span>

1. <span data-ttu-id="8efc0-181">로컬 관리자 권한으로 스크립트를 실행할 컴퓨터에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-181">Sign in to the machine that you will run the script from with local administrator rights.</span></span>

2. <span data-ttu-id="8efc0-182">GitHub에서 Get-AllTenantRulesAndForms.ps1 스크립트를 실행할 폴더로 다운로드하거나 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-182">Download or copy the Get-AllTenantRulesAndForms.ps1 script from GitHub to a folder from which you will run it.</span></span> <span data-ttu-id="8efc0-183">이 스크립트는 이 폴더 MailboxFormsExport-yyyy-mm-dd.csv 및 MailboxRulesExport-yyyy-mm-dd.csv에 2개의 날짜 스탬프가 찍힌 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-183">The script will create two date stamped files to this folder, MailboxFormsExport-yyyy-mm-dd.csv, and MailboxRulesExport-yyyy-mm-dd.csv.</span></span>

3. <span data-ttu-id="8efc0-184">PowerShell 인스턴스를 관리자로 열고 스크립트를 저장한 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-184">Open a PowerShell instance as an administrator and open the folder you saved the script to.</span></span>

4. <span data-ttu-id="8efc0-185">`.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1과 같이이 PowerShell 명령줄을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-185">Run this PowerShell command line as follows `.\Get-AllTenantRulesAndForms.ps1`.\Get-AllTenantRulesAndForms.ps1</span></span>

#### <a name="interpreting-the-output"></a><span data-ttu-id="8efc0-186">결과 해석</span><span class="sxs-lookup"><span data-stu-id="8efc0-186">Interpreting the output</span></span>

- <span data-ttu-id="8efc0-187">**MailboxRulesExport *-yyyy-mm-dd*.csv**: 응용 프로그램 또는 실행 파일이 포함된 작동 조건에 대한 규칙(행 당 하나씩)을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-187">**MailboxRulesExport-*yyyy-mm-dd*.csv**: Examine the rules (one per row) for action conditions that include applications or executables:</span></span>

  - <span data-ttu-id="8efc0-188">**ActionType(A열)**: "ID_ACTION_CUSTOM" 값이 표시되는 경우 이 규칙은 악의가 있을 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-188">**ActionType (column A)**: If you see the value "ID_ACTION_CUSTOM", the rule is likely malicious.</span></span>

  - <span data-ttu-id="8efc0-189">**IsPotentiallyMalicious(D열)**:이 값이 "TRUE" 인 경우 이 규칙은 악의가 있을 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-189">**IsPotentiallyMalicious (column D)**: If this value is "TRUE", the rule is likely malicious.</span></span>

  - <span data-ttu-id="8efc0-190">**ActionCommand(G 열)**: 이 열에 .exe 또는 .zip 확장명 또는 URL을 참조하는 알 수 없는 항목이 있는 응용 프로그램 또는 파일이 나열되는 경우 규칙이 악성일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-190">**ActionCommand (column G)**: If this column lists an application or any file with .exe or .zip extensions, or an unknown entry that refers to a URL, the rule is likely malicious.</span></span>

- <span data-ttu-id="8efc0-191">**MailboxFormsExport-*yyyy-mm-dd*.csv:** 일반적으로 사용자 지정 양식을 사용하는 경우는 거의 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-191">**MailboxFormsExport-*yyyy-mm-dd*.csv**: In general, the use of custom forms is rare.</span></span> <span data-ttu-id="8efc0-192">이 통합 문서에서 양식을 찾은 경우 해당 사용자의 사서함을 열고 양식 자체를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-192">If you find any in this workbook, you open that user's mailbox and examine the form itself.</span></span> <span data-ttu-id="8efc0-193">조직에서 의도적으로 이를 추가하지 않은 경우 악의가 있을 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-193">If your organization did not put it there intentionally, it is likely malicious.</span></span>

## <a name="how-to-stop-and-remediate-the-outlook-rules-and-forms-attack"></a><span data-ttu-id="8efc0-194">Outlook 규칙과 양식 공격을 중지하고 재구성하는 방법</span><span class="sxs-lookup"><span data-stu-id="8efc0-194">How to stop and remediate the Outlook Rules and Forms attack</span></span>

<span data-ttu-id="8efc0-195">이러한 공격에 대한 증거를 발견한 경우에는 재구성이 간단하며 사서함에서 규칙이나 양식을 삭제하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-195">If you find any evidence of either of these attacks, remediation is simple, just delete the rule or form from the mailbox.</span></span> <span data-ttu-id="8efc0-196">Outlook 클라이언트에서 이 작업을 수행하거나 원격 PowerShell을 사용하여 규칙을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-196">You can do this with the Outlook client or using remote PowerShell to remove rules.</span></span>

### <a name="using-outlook"></a><span data-ttu-id="8efc0-197">Outlook 사용</span><span class="sxs-lookup"><span data-stu-id="8efc0-197">Using Outlook</span></span>

1. <span data-ttu-id="8efc0-198">사용자가 Outlook에서 사용한 모든 장치를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-198">Identify all the devices that the user has used with Outlook.</span></span> <span data-ttu-id="8efc0-199">이들 장치 모두에서 잠정 맬웨어를 청소해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-199">They will all need to be cleaned of potential malware.</span></span> <span data-ttu-id="8efc0-200">모든 장치를 청소할 때 까지는 사용자가 로그온 하고 전자 메일을 사용하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-200">Do not allow the user to sign on and use email until all the devices are cleaned.</span></span>

2. <span data-ttu-id="8efc0-201">각 장치에 대한 [규칙 삭제](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f)에 있는 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-201">Follow the steps in [Delete a rule](https://support.microsoft.com/office/2f0e7139-f696-4422-8498-44846db9067f) for each device.</span></span>

3. <span data-ttu-id="8efc0-202">다른 맬웨어가 존재하지 않는 경우 장치에 모든 소프트웨어의 형식을 지정하고 다시 설치하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-202">If you are unsure about the presence of other malware, you can format and reinstall all the software on the device.</span></span> <span data-ttu-id="8efc0-203">모바일 장치의 경우 제조업체 단계에 따라 장치를 출하 시 이미지로 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-203">For mobile devices, you can follow the manufacturers steps to reset the device to the factory image.</span></span>

4. <span data-ttu-id="8efc0-204">최신 버전의 Outlook을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-204">Install the most up-to-date versions of Outlook.</span></span> <span data-ttu-id="8efc0-205">최신 버전의 Outlook은 기본적으로 이 두 가지 유형의 공격을 차단한다는 사실을 기억하세요.</span><span class="sxs-lookup"><span data-stu-id="8efc0-205">Remember that the current version of Outlook blocks both types of this attack by default.</span></span>

5. <span data-ttu-id="8efc0-206">사서함의 모든 오프라인 복사본이 제거된 후 사용자의 암호를 다시 설정하고(고품질의 복사본 [](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) 사용) MFA를 아직 사용하도록 설정하지 않은 경우 사용자에 대해 다단계 인증 설정의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-206">Once all offline copies of the mailbox have been removed, reset the user's password (use a high quality one) and follow the steps in [Setup multi-factor authentication for users](../../admin/security-and-compliance/set-up-multi-factor-authentication.md) if MFA has not already been enabled.</span></span> <span data-ttu-id="8efc0-207">이렇게 하면 사용자의 자격 증명이 다른 수단(예: 피싱 또는 암호 재사용)을 통해 노출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-207">This ensures that the user's credentials are not exposed via other means (such as phishing or password re-use).</span></span>

### <a name="using-powershell"></a><span data-ttu-id="8efc0-208">PowerShell 사용</span><span class="sxs-lookup"><span data-stu-id="8efc0-208">Using PowerShell</span></span>

<span data-ttu-id="8efc0-209">위험한 규칙을 제거하거나 해제하는 데 사용할 수 있는 두 개의 원격 PowerShell cmdlet이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-209">There are two remote PowerShell cmdlets you can use to remove or disable dangerous rules.</span></span> <span data-ttu-id="8efc0-210">다음의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-210">Just follow the steps.</span></span>

#### <a name="steps-for-mailboxes-that-are-on-an-exchange-server"></a><span data-ttu-id="8efc0-211">Exchange 서버에 있는 사서함에 대한 단계</span><span class="sxs-lookup"><span data-stu-id="8efc0-211">Steps for mailboxes that are on an Exchange server</span></span>

1. <span data-ttu-id="8efc0-212">원격 PowerShell을 사용하여 Exchange 서버에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-212">Connect to the Exchange server using remote PowerShell.</span></span> <span data-ttu-id="8efc0-213">[원격 PowerShell을 사용하여 Exchange 서버에 연결](/powershell/exchange/connect-to-exchange-servers-using-remote-powershell)에 있는 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-213">Follow the steps in [Connect to Exchange servers using remote PowerShell](/powershell/exchange/connect-to-exchange-servers-using-remote-powershell).</span></span>

2. <span data-ttu-id="8efc0-214">사서함의 단일 규칙, 여러 규칙 또는 모든 규칙을 완전히 제거하려면 [InboxRule 제거](/powershell/module/exchange/Remove-InboxRule) cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-214">If you want to completely remove a single rule, multiple rules, or all rules from a mailbox use the [Remove-InboxRule](/powershell/module/exchange/Remove-InboxRule) cmdlet.</span></span>

3. <span data-ttu-id="8efc0-215">추가 조사를 위해 규칙과 해당 콘텐츠를 보존하려면 [InboxRule 비활성화](/powershell/module/exchange/disable-inboxrule) cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-215">If you want to retain the rule and its contents for further investigation use the [Disable-InboxRule](/powershell/module/exchange/disable-inboxrule) cmdlet.</span></span>

#### <a name="steps-for-mailboxes-in-exchange-online"></a><span data-ttu-id="8efc0-216">Exchange Online의 사서함에 대한 단계</span><span class="sxs-lookup"><span data-stu-id="8efc0-216">Steps for mailboxes in Exchange Online</span></span>

1. <span data-ttu-id="8efc0-217">[PowerShell을 사용하여 Exchange Online에 연결](/powershell/exchange/connect-to-exchange-online-powershell)에 있는 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-217">Follow the steps in [Connect to Exchange Online using PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="8efc0-218">사서함의 단일 규칙, 여러 규칙 또는 모든 규칙을 완전히 제거하려면 [받은 편지함 제거 규칙](/powershell/module/exchange/Remove-InboxRule) cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-218">If you want to completely remove a single rule, multiple rules, or all rules from a mailbox use the [Remove-Inbox Rule](/powershell/module/exchange/Remove-InboxRule) cmdlet.</span></span>

3. <span data-ttu-id="8efc0-219">추가 조사를 위해 규칙과 해당 콘텐츠를 보존하려면 [InboxRule 비활성화](/powershell/module/exchange/disable-inboxrule) cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-219">If you want to retain the rule and its contents for further investigation use the [Disable-InboxRule](/powershell/module/exchange/disable-inboxrule) cmdlet.</span></span>

## <a name="how-to-minimize-future-attacks"></a><span data-ttu-id="8efc0-220">미래의 공격을 최소화하는 방법</span><span class="sxs-lookup"><span data-stu-id="8efc0-220">How to minimize future attacks</span></span>

### <a name="first-protect-your-accounts"></a><span data-ttu-id="8efc0-221">첫 번째: 계정 보호</span><span class="sxs-lookup"><span data-stu-id="8efc0-221">First: protect your accounts</span></span>

<span data-ttu-id="8efc0-222">사용자 계정 중 하나를 도난 혹은 침해를 받은 경우에만 공격자가 이 규칙과 양식을 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-222">The Rules and Forms exploits are only used by an attacker after they have stolen or breached one of your user's accounts.</span></span> <span data-ttu-id="8efc0-223">따라서 조직에서 이러한 악용을 방지하는 첫 번째 단계는 사용자 계정을 적극적으로 보호하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-223">So, your first step to preventing the use of these exploits against your organization is to aggressively protect your user accounts.</span></span> <span data-ttu-id="8efc0-224">계정이 침해되는 가장 일반적인 방법 중 일부는 피싱 또는 암호 분무 공격을 [통해서입니다.](https://www.microsoft.com/security/blog/2020/04/23/protecting-organization-password-spray-attacks/)</span><span class="sxs-lookup"><span data-stu-id="8efc0-224">Some of the most common ways that accounts are breached are through phishing or [password spray attacks](https://www.microsoft.com/security/blog/2020/04/23/protecting-organization-password-spray-attacks/).</span></span>

<span data-ttu-id="8efc0-225">사용자 계정 및 특히 관리자 계정을 보호하는 가장 좋은 방법은 사용자에 대해 다단계 [인증을 설정하는 것입니다.](../../admin/security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="8efc0-225">The best way to protect your user accounts, and especially your administrator accounts, is to [set up multi-factor authentication for users](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span> <span data-ttu-id="8efc0-226">사용자는 또한:</span><span class="sxs-lookup"><span data-stu-id="8efc0-226">You should also:</span></span>

- <span data-ttu-id="8efc0-227">사용자 계정이 [액세스되고 사용되는](/azure/active-directory/active-directory-view-access-usage-reports) 방식을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-227">Monitor how your user accounts are [accessed and used](/azure/active-directory/active-directory-view-access-usage-reports).</span></span> <span data-ttu-id="8efc0-228">초기 침해를 방지하지 못할 수 있지만 침해의 기간과 영향은 더 일찍 발견하여 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-228">You may not prevent the initial breach, but you will shorten the duration and the impact of the breach by detecting it sooner.</span></span> <span data-ttu-id="8efc0-229">[Office 365 클라우드 앱 보안 정책](/cloud-app-security/what-is-cloud-app-security)을 사용 하여 계정을 모니터링하고 비정상적 활동에 대 한 알림을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-229">You can use these [Office 365 Cloud App Security policies](/cloud-app-security/what-is-cloud-app-security) to monitor you accounts and alert on unusual activity:</span></span>

  - <span data-ttu-id="8efc0-230">**로그인 시도의 수차례 실패**: 이 정책은 침해의 시도를 나타낼 수 있는 학습한 기준을 고려하여 단일 세션에서 수차례 로그인 활동에 실패하는 경우 사용자 환경을 프로파일링하고 알림을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-230">**Multiple failed login attempts**: This policy profiles your environment and triggers alerts when users perform multiple failed login activities in a single session with respect to the learned baseline, which could indicate an attempted breach.</span></span>

  - <span data-ttu-id="8efc0-231">**불가능한 이동**: 이 정책은 사용자 환경을 프로파일링하고 두 위치 사이의 예상 이동 시간 보다 짧은 기간에 여러 위치에 있는 같은 사용자의 다른 위치에서의 활동을 탐지하는 경우 알림을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-231">**Impossible travel**: This policy profiles your environment and triggers alerts when activities are detected from the same user in different locations within a time period that is shorter than the expected travel time between the two locations.</span></span> <span data-ttu-id="8efc0-232">이는 다른 사용자가 동일한 자격 증명을 사용 하고 있음을 의미할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-232">This could indicate that a different user is using the same credentials.</span></span> <span data-ttu-id="8efc0-233">이 비정상 동작의 탐지는 새 사용자의 활동 패턴을 학습하는 동안 초기 7일의 학습 기간을 필요로 합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-233">Detecting this anomalous behavior necessitates an initial learning period of seven days during which it learns a new user's activity pattern.</span></span>

  - <span data-ttu-id="8efc0-234">**비정상적 가장 활동(사용자)**: 이 정책은 침해의 시도를 나타낼 수 있는 학습한 기준을 고려하여 단일 세션에서 수차례 가장 활동을 수행하는 경우 사용자 환경을 프로파일링하고 알림을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-234">**Unusual impersonated activity (by user)**: This policy profiles your environment and triggers alerts when users perform multiple impersonated activities in a single session with respect to the baseline learned, which could indicate an attempted breach.</span></span>

- <span data-ttu-id="8efc0-235">[Office 365 보안](https://securescore.office.com/) 점수와 같은 도구를 사용하여 계정 보안 구성 및 동작을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-235">Use a tool like [Office 365 Secure Score](https://securescore.office.com/) to manage account security configurations and behaviors.</span></span>

### <a name="second-keep-your-outlook-clients-current"></a><span data-ttu-id="8efc0-236">두 번째: Outlook 클라이언트를 최신 상태로 유지</span><span class="sxs-lookup"><span data-stu-id="8efc0-236">Second: Keep your Outlook clients current</span></span>

<span data-ttu-id="8efc0-237">완전히 업데이트 및 패치된 버전의 Outlook 2013 및 2016에서는 기본적으로 "응용 프로그램 시작" 규칙/양식 작업을 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-237">Fully updated and patched versions of Outlook 2013, and 2016 disable the "Start Application" rule/form action by default.</span></span> <span data-ttu-id="8efc0-238">이렇게 하면 공격자가 계정을 침해하는 경우에도 규칙 및 양식 작업이 차단됩니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-238">This will ensure that even if an attacker breaches the account, the rule and form actions will be blocked.</span></span> <span data-ttu-id="8efc0-239">[Office 업데이트 설치](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5)단계를 따라 최신 업데이트 및 보안 패치를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-239">You can install the latest updates and security patches by following the steps in [Install Office updates](https://support.microsoft.com/office/2ab296f3-7f03-43a2-8e50-46de917611c5).</span></span>

<span data-ttu-id="8efc0-240">다음은 Outlook 2013 및 2016 클라이언트용 패치 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-240">Here are the patch versions for your Outlook 2013 and 2016 clients:</span></span>

- <span data-ttu-id="8efc0-241">**Outlook 2016**: 16.0.4534.1001 이상.</span><span class="sxs-lookup"><span data-stu-id="8efc0-241">**Outlook 2016**: 16.0.4534.1001 or greater.</span></span>

- <span data-ttu-id="8efc0-242">**Outlook 2013**: 15.0.4937.1000 이상.</span><span class="sxs-lookup"><span data-stu-id="8efc0-242">**Outlook 2013**: 15.0.4937.1000 or greater.</span></span>

<span data-ttu-id="8efc0-243">개별 보안 패치에 대한 자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8efc0-243">For more information on the individual security patches, see:</span></span>

- [<span data-ttu-id="8efc0-244">Outlook 2016 보안 패치</span><span class="sxs-lookup"><span data-stu-id="8efc0-244">Outlook 2016 Security Patch</span></span>](https://support.microsoft.com/help/3191883)

- [<span data-ttu-id="8efc0-245">Outlook 2013 보안 패치</span><span class="sxs-lookup"><span data-stu-id="8efc0-245">Outlook 2013 Security Patch</span></span>](https://support.microsoft.com/help/3191938)

### <a name="third-monitor-your-outlook-clients"></a><span data-ttu-id="8efc0-246">세 번째: Outlook 클라이언트 모니터링</span><span class="sxs-lookup"><span data-stu-id="8efc0-246">Third: Monitor your Outlook clients</span></span>

<span data-ttu-id="8efc0-247">패치 및 업데이트가 설치되어 있더라도 공격자가 로컬 컴퓨터 구성을 변경하여 "응용 프로그램 시작" 동작을 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-247">Note that even with the patches and updates installed, it is possible for an attacker to change the local machine configuration to re-enable the "Start Application" behavior.</span></span> <span data-ttu-id="8efc0-248">[고급 그룹 정책 관리](/microsoft-desktop-optimization-pack/agpm/)를 사용하여 클라이언트에서 로컬 컴퓨터 정책을 모니터링하고 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-248">You can use [Advanced Group Policy Management](/microsoft-desktop-optimization-pack/agpm/) to monitor and enforce local machine policies on your clients.</span></span>

<span data-ttu-id="8efc0-249">[64비트 버전의 Windows를](https://support.microsoft.com/help/305097)사용하여 시스템 레지스트리를 보는 방법의 정보를 사용하여 레지스트리의 재지정을 통해 "응용 프로그램 시작"이 다시 활성화되어 있는지 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-249">You can see if "Start Application" has been re-enabled through an override in the registry by using the information in [How to view the system registry by using 64-bit versions of Windows](https://support.microsoft.com/help/305097).</span></span> <span data-ttu-id="8efc0-250">다음의 하위 키를 확인합니다:</span><span class="sxs-lookup"><span data-stu-id="8efc0-250">Check these subkeys:</span></span>

- <span data-ttu-id="8efc0-251">**Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`</span><span class="sxs-lookup"><span data-stu-id="8efc0-251">**Outlook 2016**: `HKEY_CURRENT_USER\Software\Microsoft\Office\16.0\Outlook\Security\`</span></span>

- <span data-ttu-id="8efc0-252">**Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`</span><span class="sxs-lookup"><span data-stu-id="8efc0-252">**Outlook 2013**: `HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Outlook\Security\`</span></span>

<span data-ttu-id="8efc0-253">EnableUnsafeClientMailRules 키를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-253">Look for the key EnableUnsafeClientMailRules.</span></span> <span data-ttu-id="8efc0-254">찾았고 1로 설정되어 있으면 Outlook 보안 패치가 오버라이드되었고 컴퓨터가 양식/규칙 공격에 취약합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-254">If it is there and is set to 1, the Outlook security patch has been overridden and the computer is vulnerable to the Form/Rules attack.</span></span> <span data-ttu-id="8efc0-255">값이 0 이면 "응용 프로그램 시작" 작업을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-255">If the value is 0, the "Start Application" action is disabled.</span></span> <span data-ttu-id="8efc0-256">업데이트되고 패치가 적용된 버전의 Outlook이 설치되었고 이 레지스트리 키가 없는 경우에는 시스템이 이러한 공격에 취약하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-256">If the updated and patched version of Outlook is installed and this registry key is not present, then a system is not vulnerable to these attacks.</span></span>

<span data-ttu-id="8efc0-257">온-프레미스 Exchange 설치를 사용하는 고객은 사용 가능한 패치가 없는 이전 버전의 Outlook을 차단하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-257">Customers with on-premises Exchange installations should consider blocking older versions of Outlook that do not have patches available.</span></span> <span data-ttu-id="8efc0-258">이 프로세스에 대한 자세한 내용은 [Outlook 클라이언트 차단 구성](/exchange/configure-outlook-client-blocking-exchange-2013-help) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8efc0-258">Details on this process can be found in the article [Configure Outlook client blocking](/exchange/configure-outlook-client-blocking-exchange-2013-help).</span></span>

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="8efc0-259">사이버 보안 프로그램과 같은 Microsoft 365 보안</span><span class="sxs-lookup"><span data-stu-id="8efc0-259">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="8efc0-260">Microsoft 365 구독에는 데이터 및 사용자를 보호하는 데 사용할 수 있는 강력한 보안 기능이 함께 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-260">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span> <span data-ttu-id="8efc0-261">[Microsoft 365 보안 로드맵 - 최초 30일, 90일 및 그 이후의 최우선 순위](security-roadmap.md)를 사용하여 Microsoft에서 권장하는 Microsoft 365 테넌트 보안을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-261">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 tenant.</span></span>

- <span data-ttu-id="8efc0-262">처음 30일 이내에 수행 할 작업</span><span class="sxs-lookup"><span data-stu-id="8efc0-262">Tasks to accomplish in the first 30 days.</span></span> <span data-ttu-id="8efc0-263">이는 즉시 영향을 미치며 사용자에게 낮은 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-263">These have immediate effect and are low-impact to your users.</span></span>

- <span data-ttu-id="8efc0-264">90일 이내에 수행해야 할 작업</span><span class="sxs-lookup"><span data-stu-id="8efc0-264">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="8efc0-265">이러한 작업들은 계획하고 구현하는 데 다소 시간이 걸리지만 보안 태세를 갖추는 데 큰 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-265">These take a bit more time to plan and implement but greatly improve your security posture.</span></span>

- <span data-ttu-id="8efc0-266">90일 초과</span><span class="sxs-lookup"><span data-stu-id="8efc0-266">Beyond 90 days.</span></span> <span data-ttu-id="8efc0-267">이러한 향상된 기능은 처음 90일간의 작업에서 구축됩니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-267">These enhancements build in your first 90 days work.</span></span>

## <a name="see-also"></a><span data-ttu-id="8efc0-268">참고 항목:</span><span class="sxs-lookup"><span data-stu-id="8efc0-268">See also:</span></span>

- <span data-ttu-id="8efc0-269">규칙 벡터에 대한 SilentBreak 보안 게시물 [악의적 Outlook 규칙](https://silentbreaksecurity.com/malicious-outlook-rules/)은 Outlook 규칙에 대한 자세한 검토를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-269">[Malicious Outlook Rules](https://silentbreaksecurity.com/malicious-outlook-rules/) by SilentBreak Security Post about Rules Vector provides a detailed review of how the Outlook Rules.</span></span>

- <span data-ttu-id="8efc0-270">Mailrule Pwnage에 대한 Sensepost 블로그 [HTTP 및 Mailrule Pwnage를 통한 MAPI](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/)는 Outlook 규칙을 통해 사서함을 이용하게 해주는 Ruler라는 도구에 대해 설명을 합니다.</span><span class="sxs-lookup"><span data-stu-id="8efc0-270">[MAPI over HTTP and Mailrule Pwnage](https://sensepost.com/blog/2016/mapi-over-http-and-mailrule-pwnage/) on the Sensepost blog about Mailrule Pwnage discusses a tool called Ruler that lets you exploit mailboxes through Outlook rules.</span></span>

- <span data-ttu-id="8efc0-271">양식 위협 벡터에 대한 Sensepost 블로그의 [Outlook 양식 및 셸](https://sensepost.com/blog/2017/outlook-forms-and-shells/)</span><span class="sxs-lookup"><span data-stu-id="8efc0-271">[Outlook forms and shells](https://sensepost.com/blog/2017/outlook-forms-and-shells/) on the Sensepost blog about Forms Threat Vector.</span></span>

- [<span data-ttu-id="8efc0-272">Ruler 코드 베이스</span><span class="sxs-lookup"><span data-stu-id="8efc0-272">Ruler Codebase</span></span>](https://github.com/sensepost/ruler)

- [<span data-ttu-id="8efc0-273">Ruler 위험 노출 표시기</span><span class="sxs-lookup"><span data-stu-id="8efc0-273">Ruler Indicators of Compromise</span></span>](https://github.com/sensepost/notruler/blob/master/iocs.md)