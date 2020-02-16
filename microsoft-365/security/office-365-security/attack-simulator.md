---
title: Office 365의 공격 시뮬레이터
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: Office 365 전역 관리자는 공격 시뮬레이터를 사용 하 여 조직에서 현실적인 공격 시나리오를 실행할 수 있습니다. 이를 통해 실질적인 공격이 비즈니스에 방문 하기 전에 취약 한 사용자를 식별 하 고 찾을 수 있습니다.
ms.openlocfilehash: 93a2601322fd33024c1310e1df69ad1dea2f07b7
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42083695"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="08392-104">Office 365의 공격 시뮬레이터</span><span class="sxs-lookup"><span data-stu-id="08392-104">Attack Simulator in Office 365</span></span>

<span data-ttu-id="08392-105">**요약** Office 365 전역 관리자 또는 보안 관리자이 고 조직에 [위협 조사 및 응답 기능이](office-365-ti.md)포함 된 Office 365 Advanced Threat Protection 계획 2가 있는 경우 공격 시뮬레이터를 사용 하 여 조직에서 현실적인 공격 시나리오를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-105">**Summary** If you are an Office 365 global administrator or a security administrator and your organization has Office 365 Advanced Threat Protection Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="08392-106">이를 통해 실질적인 공격이 수익에 영향을 미치기 전에 취약한 사용자를 식별하고 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-106">This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="08392-107">자세한 내용은이 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="08392-107">Read this article to learn more.</span></span>

## <a name="the-attacks"></a><span data-ttu-id="08392-108">공격</span><span class="sxs-lookup"><span data-stu-id="08392-108">The Attacks</span></span>

<span data-ttu-id="08392-109">현재 세 가지 유형의 공격 시뮬레이션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-109">Three kinds of attack simulations are currently available:</span></span>

- [<span data-ttu-id="08392-110">자격 증명 수집 스피어-피싱 공격</span><span class="sxs-lookup"><span data-stu-id="08392-110">Credential harvest spear-phishing attack</span></span>](#credential-harvest-spear-phishing-attack)

- [<span data-ttu-id="08392-111">첨부 파일 스피어-피싱 공격</span><span class="sxs-lookup"><span data-stu-id="08392-111">Attachment spear-phishing attack</span></span>](#attachment-spear-phishing-attack)

- [<span data-ttu-id="08392-112">암호 스프레이 공격</span><span class="sxs-lookup"><span data-stu-id="08392-112">Password-spray attack</span></span>](#password-spray-attack)

- [<span data-ttu-id="08392-113">무제한 비밀번호 공격</span><span class="sxs-lookup"><span data-stu-id="08392-113">Brute-force password attack</span></span>](#brute-force-password-attack)

<span data-ttu-id="08392-114">공격이 정상적으로 시작 되려면 시뮬레이트된 공격을 실행 하는 데 사용 하는 계정이 다단계 인증을 사용 하 고 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-114">For an attack to be successfully launched, make sure that the account you are using to run simulated attacks is using multi-factor authentication.</span></span> <span data-ttu-id="08392-115">또한 Office 365 전역 관리자 또는 보안 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-115">In addition, you must be an Office 365 global administrator or a security administrator.</span></span> <span data-ttu-id="08392-116">역할 및 사용 권한에 대 한 자세한 내용은 [Office 365 보안 & 준수 센터의 사용 권한을](permissions-in-the-security-and-compliance-center.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="08392-116">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

<span data-ttu-id="08392-117">공격 시뮬레이터에 액세스 &amp; 하려면 보안 및 준수 센터에서 **위협 관리** \> **공격 시뮬레이터**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-117">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="08392-118">시작하기 전에...</span><span class="sxs-lookup"><span data-stu-id="08392-118">Before you begin...</span></span>

<span data-ttu-id="08392-119">사용자와 조직이 공격 시뮬레이터에 대해 다음 요구 사항을 충족 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-119">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>

- <span data-ttu-id="08392-120">조직의 전자 메일이 Exchange Online에서 호스트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08392-120">Your organization's email is hosted in Exchange Online.</span></span> <span data-ttu-id="08392-121">온-프레미스 전자 메일 서버에는 Attack 시뮬레이터를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-121">(Attack Simulator is not available for on-premises email servers.)</span></span>

- <span data-ttu-id="08392-122">Office 365 전역 관리자 또는 보안 관리자 인 경우</span><span class="sxs-lookup"><span data-stu-id="08392-122">You are an Office 365 global administrator or security administrator</span></span>

- <span data-ttu-id="08392-123">피싱 캠페인은 30 일 동안 이벤트를 수집 하 고 처리 하며, 캠페인을 시작한 후 최대 90 일 동안 기록 캠페인 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-123">Phishing campaigns will collect and process events for a period of 30 days, historical campaign data will be available for up to 90 days after the campaign is launched.</span></span>

- <span data-ttu-id="08392-124">하나 이상의 Office 365 전역 관리자 계정 및 보안 관리자에 게 공격 시뮬레이터를 사용할 수 있도록 [다단계 인증/조건부 액세스가](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) 설정 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-124">[Multi-factor authentication/Conditional Access](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) is turned on, for at least the Office 365 global administrator account and security administrators who will be using Attack Simulator.</span></span> <span data-ttu-id="08392-125">이상적으로는 조직의 모든 사용자에 대해 다단계 인증/조건부 액세스를 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-125">(Ideally, multi-factor authentication/conditional access is turned on for all users in your organization.)</span></span>

- <span data-ttu-id="08392-126">조직에 [Office 365 Advanced Threat Protection 계획 2](office-365-atp.md)가 있으며, 보안 &amp; 및 준수 센터에서 공격 시뮬레이터가 표시 됩니다 ( **위협 관리** \> **공격 시뮬레이터**로 이동).</span><span class="sxs-lookup"><span data-stu-id="08392-126">Your organization has [Office 365 Advanced Threat Protection Plan 2](office-365-atp.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span>

    ![위협 관리-공격 시뮬레이터](../../media/ThreatMgmt-AttackSimulator.png)

## <a name="credential-harvest-spear-phishing-attack"></a><span data-ttu-id="08392-128">자격 증명 수집 스피어-피싱 공격</span><span class="sxs-lookup"><span data-stu-id="08392-128">Credential harvest spear-phishing attack</span></span>

<span data-ttu-id="08392-129">피싱은 사회 공학적 스타일 공격으로 classed 다양 한 공격 집합에 대 한 일반 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="08392-129">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack.</span></span> <span data-ttu-id="08392-130">이 공격은 특정 개인 또는 조직 그룹을 목표로 하는 스피어 피싱에 중점을 두었습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-130">This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization.</span></span> <span data-ttu-id="08392-131">일반적으로 일부 정찰 자가 수행 하는 사용자 지정 된 공격과 받는 사람에 게 신뢰를 생성 하는 표시 이름 (예: 조직의 임원 으로부터 온 것 처럼 보이는 전자 메일 메시지)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-131">Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>

<span data-ttu-id="08392-132">이 공격은 표시 이름과 원본 주소를 변경 하 여 메시지를 보낸 사람을 조작할 수 있는 방법을 중점적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-132">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address.</span></span> <span data-ttu-id="08392-133">스피어-피싱 공격이 성공 하면 cyberattackers에서 사용자 자격 증명에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-133">When spear-phishing attacks are successful, cyberattackers gain access to users' credentials.</span></span>

### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="08392-134">스피어 피싱 공격을 시뮬레이션 하려면</span><span class="sxs-lookup"><span data-stu-id="08392-134">To simulate a spear-phishing attack</span></span>

![전자 메일 본문 작성](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

<span data-ttu-id="08392-136">**전자 메일 본문** 필드 자체에서 서식 있는 html 편집기를 직접 만들거나 HTML 원본으로 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-136">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source.</span></span>

1. <span data-ttu-id="08392-137">[보안 &amp; 및 준수 센터](https://protection.office.com)에서 **위협 관리** \> **공격 시뮬레이터**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-137">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="08392-138">공격에 대 한 의미 있는 캠페인 이름을 지정 하거나 서식 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-138">Specify a meaningful campaign name for the attack or select a template.</span></span>

   ![피싱 시작 페이지](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

3. <span data-ttu-id="08392-140">대상 받는 사람을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-140">Specify the target recipients.</span></span> <span data-ttu-id="08392-141">조직의 개인 또는 그룹이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-141">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="08392-142">공격이 성공 하려면 각 대상이 지정 된 받는 사람에 게 Exchange Online 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-142">Each targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>

   ![받는 사람 선택](../../media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)

4. <span data-ttu-id="08392-144">피싱 메일 세부 정보를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-144">Configure the Phishing email details.</span></span>

   ![전자 메일 세부 정보 구성](../../media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)

   <span data-ttu-id="08392-146">HTML 서식 지정은 캠페인 요구 사항에 따라 복잡할 수도 있고 기본 형식이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-146">The HTML formatting can be as complex or basic as your campaign needs.</span></span> <span data-ttu-id="08392-147">전자 메일 형식이 HTML 인 것 처럼 이미지와 텍스트를 삽입 하 여 believability을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-147">As the email format is HTML, you can insert images and text to enhance believability.</span></span> <span data-ttu-id="08392-148">수신 되는 전자 메일 클라이언트에서 받은 메시지의 모양을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-148">You have control on what the received message will look like in the receiving email client.</span></span>

5. <span data-ttu-id="08392-149">**보낸 사람 (이름)** 필드에 대 한 텍스트를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-149">Specify text for the **From (Name)** field.</span></span> <span data-ttu-id="08392-150">받는 전자 메일 클라이언트의 **표시 이름** 에이 필드를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-150">This is the field that shows in the **Display Name** in the receiving email client.</span></span>

6. <span data-ttu-id="08392-151">텍스트 또는 **보낸 사람** 필드를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-151">Specify text or the **From** field.</span></span> <span data-ttu-id="08392-152">받는 전자 메일 클라이언트에 있는 보낸 사람의 전자 메일 주소로 표시 되는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="08392-152">This is the field that shows as the email address of the sender in the receiving email client.</span></span>

   <span data-ttu-id="08392-153">조직 내에서 기존 전자 메일 네임 스페이스를 입력할 수 있습니다 (이 작업을 수행 하면 전자 메일 주소가 받는 클라이언트에서 실제로 확인 되 고, 매우 높은 신뢰 모델이 촉진 됨), 외부 전자 메일 주소를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-153">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address.</span></span> <span data-ttu-id="08392-154">지정한 전자 메일 주소가 실제로 존재 하는 것은 아니지만,와 `user@domainname.extension`같은 유효한 SMTP 주소의 형식을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-154">The email address that you specify does not have to actually exist, but it does need to follow the format of a valid SMTP address, such as `user@domainname.extension`.</span></span>

7. <span data-ttu-id="08392-155">드롭다운 선택기를 사용 하 여 공격에 포함 될 콘텐츠 유형을 반영 하는 피싱 로그인 서버 URL을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-155">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack.</span></span> <span data-ttu-id="08392-156">문서 배달, 기술, 급여 등의 다양 한 테마가 지정 된 Url을 선택할 수 있습니다. 이 URL은 대상 사용자가 클릭 하 라는 메시지가 표시 되는 경우 효과적입니다.</span><span class="sxs-lookup"><span data-stu-id="08392-156">Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>

8. <span data-ttu-id="08392-157">사용자 지정 랜딩 페이지 URL을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-157">Specify a custom landing page URL.</span></span> <span data-ttu-id="08392-158">이 방법을 사용 하면 사용자가 공격이 완료 되 면 지정한 URL로 리디렉션됩니다.</span><span class="sxs-lookup"><span data-stu-id="08392-158">Using this will redirect users to a URL you specify at the end of a successful attack.</span></span> <span data-ttu-id="08392-159">예를 들어 내부 인식 교육이 있는 경우 여기에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-159">If you have internal awareness training, for example, you can specify that here.</span></span>

9. <span data-ttu-id="08392-160">**제목** 필드에 대 한 텍스트를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-160">Specify text for the **Subject** field.</span></span> <span data-ttu-id="08392-161">받는 전자 메일 클라이언트에서 **주체 이름** 으로 표시 되는 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="08392-161">This is the field that shows as the **Subject Name** in the receiving email client.</span></span>

10. <span data-ttu-id="08392-162">대상이 받게 될 **전자 메일 본문** 을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-162">Compose the **Email body** that the target will receive.</span></span>

    <span data-ttu-id="08392-163">`${username}`전자 메일 본문에 대상 이름을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-163">`${username}` inserts the targets name into the Email body.</span></span>

    <span data-ttu-id="08392-164">`${loginserverurl}`대상 사용자가 클릭 하도록 할 URL을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-164">`${loginserverurl}` inserts the URL we want target users to click</span></span>

11. <span data-ttu-id="08392-165">**다음을** 선택 하 고 **마침을** 클릭 하 여 공격을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-165">Choose **Next,** then **Finish** to launch the attack.</span></span> <span data-ttu-id="08392-166">스피어 피싱 전자 메일 메시지는 대상 받는 사람의 사서함으로 배달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08392-166">The spear phishing email message is delivered to your target recipients' mailboxes.</span></span>

## <a name="attachment-spear-phishing-attack"></a><span data-ttu-id="08392-167">첨부 파일 스피어-피싱 공격</span><span class="sxs-lookup"><span data-stu-id="08392-167">Attachment spear-phishing attack</span></span>

<span data-ttu-id="08392-168">피싱은 사회 공학적 스타일 공격으로 classed 다양 한 공격 집합에 대 한 일반 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="08392-168">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack.</span></span> <span data-ttu-id="08392-169">이 공격은 개인 또는 조직에 대 한 특정 그룹을 목표로 하는 첨부 파일 스피어 피싱에 집중 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-169">This attack is focused on attachment spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization.</span></span> <span data-ttu-id="08392-170">일반적으로 일부 정찰 자가 수행 하는 사용자 지정 된 공격과 받는 사람에 게 신뢰를 생성 하는 표시 이름 (예: 조직의 임원 으로부터 온 것 처럼 보이는 전자 메일 메시지)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-170">Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>

<span data-ttu-id="08392-171">이 공격은 메시지 표시 이름 및 원본 주소를 변경 하는 것 처럼 보이는 사용자를 조작 하는 데 중점을 둔 반면,이 시간은 최종 사용자가 클릭 하는 데 사용할 수 있는 URL을 제공 하는 것이 아니라 t를 가져올 수 있는 첨부 파일을 제공 합니다. 최종 사용자가 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-171">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address, but this time as opposed to offering a URL to try and lure the end user to click, we offer an attachment that we are trying to get the end user to open.</span></span> 

### <a name="to-simulate-a-attachment-spear-phishing-attack"></a><span data-ttu-id="08392-172">첨부 파일 스피어 피싱 공격을 시뮬레이션 하려면</span><span class="sxs-lookup"><span data-stu-id="08392-172">To simulate a Attachment spear-phishing attack</span></span>

1. <span data-ttu-id="08392-173">앞에서 설명한 단계를 수행 하 여이 시간이 랜딩 페이지에서 **첨부 파일 공격** 을 클릭 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="08392-173">Follow the steps from above, having this time clicked on **Attachment Attack** on the landing page.</span></span>

2. <span data-ttu-id="08392-174">마법사를 진행 하면서 구성할 두 가지 옵션이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08392-174">As you progress through the wizard, you see two options to configure.</span></span> <span data-ttu-id="08392-175">**첨부 파일 형식은**두 개의 첨부 파일 형식인 **.docx** 또는 **.pdf**를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-175">The **Attachment Type**, we support two attachment types, **.docx** or **.pdf**.</span></span> <span data-ttu-id="08392-176">**첨부 파일 이름**입니다 .이 필드를 사용 하 여 캠페인에 대 한 의미 있는 첨부 파일 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="08392-176">The **Attachment Name**, use this field to create a meaningful attachment name for the campaign.</span></span>

## <a name="password-spray-attack"></a><span data-ttu-id="08392-177">암호 스프레이 공격</span><span class="sxs-lookup"><span data-stu-id="08392-177">Password-spray attack</span></span>

<span data-ttu-id="08392-178">조직에 대 한 암호 분무 공격은 잘못 된 행위자가 테 넌 트에서 유효한 사용자 목록을 성공적으로 가져온 후에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08392-178">A password spray attack against an organization is typically used after a bad actor has successfully acquired a list of valid users from the tenant.</span></span> <span data-ttu-id="08392-179">잘못 된 행위자가 사용자 들이 사용 하는 일반적인 암호를 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-179">The bad actor knows about common passwords that people use.</span></span> <span data-ttu-id="08392-180">이 공격은 많이 사용 되는 공격으로, 실행 하는 데 비용이 적게 드는 공격이 며 무작위 접근 방식 보다 감지 하기가 더 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-180">This is a widely used attack, as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>

<span data-ttu-id="08392-181">이 공격은 대규모 대상 기반 사용자에 대해 공통 암호를 지정할 수 있도록 하는 데 중점을 둔 것입니다.</span><span class="sxs-lookup"><span data-stu-id="08392-181">This attack focuses on letting you specify a common password against a large target base of users.</span></span>

<span data-ttu-id="08392-182">**중요 참고** 다단계 인증을 이미 사용 하는 최종 사용자 계정에 대해 암호 분무 공격을 실행 하면 보고에 해당 계정에 대 한 실패 시도가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-182">**Important Note** running the password spray attack against end user accounts that already have multi-factor authentication, will result in a unsuccessful attempt for those accounts in the reporting.</span></span> <span data-ttu-id="08392-183">이는 multi-factor authentication이 암호 분무 공격 으로부터 보호 하는 데 도움이 되는 기본 mechanims 중 하나 이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="08392-183">This is due to multi-factor authentication being one of the primary mechanims to help protect against password spray attacks, so is expected.</span></span>

### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="08392-184">암호 분무 공격을 시뮬레이션 하려면</span><span class="sxs-lookup"><span data-stu-id="08392-184">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="08392-185">[보안 &amp; 및 준수 센터](https://protection.office.com)에서 **위협 관리** \> **공격 시뮬레이터**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-185">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="08392-186">공격에 대해 의미 있는 캠페인 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-186">Specify a meaningful campaign name for the attack.</span></span>

3. <span data-ttu-id="08392-187">대상 받는 사람을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-187">Specify the target recipients.</span></span> <span data-ttu-id="08392-188">조직의 개인 또는 그룹이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-188">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="08392-189">공격이 성공 하려면 대상 받는 사람에 게 Exchange Online 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-189">A targeted recipient must have an Exchange Online mailbox in order for the attack to be successful.</span></span>

4. <span data-ttu-id="08392-190">공격에 사용할 암호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-190">Specify a password to use for the attack.</span></span> <span data-ttu-id="08392-191">예를 들어 사용자가 시도할 수 있는 공통적이 고 관련 `Summer2019`암호는 한 가지입니다.</span><span class="sxs-lookup"><span data-stu-id="08392-191">For example, one common, relevant password you could try is `Summer2019`.</span></span> <span data-ttu-id="08392-192">다른 것은 `Fall2019`또는 `Password1`입니다.</span><span class="sxs-lookup"><span data-stu-id="08392-192">Another might be `Fall2019`, or `Password1`.</span></span>

5. <span data-ttu-id="08392-193">**마침을** 선택 하 여 공격을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-193">Choose **Finish** to launch the attack.</span></span>

## <a name="brute-force-password-attack"></a><span data-ttu-id="08392-194">무제한 비밀번호 공격</span><span class="sxs-lookup"><span data-stu-id="08392-194">Brute-force password attack</span></span>

<span data-ttu-id="08392-195">조직에 대 한 무작위 암호 공격은 잘못 된 행위자가 테 넌 트에서 주요 사용자 목록을 성공적으로 가져온 후에 일반적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="08392-195">A brute-force password attack against an organization is typically used after a bad actor has successfully acquired a list of key users from the tenant.</span></span> <span data-ttu-id="08392-196">이 공격은 단일 사용자 계정에 대 한 암호 집합 시도에 집중 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-196">This attack focuses on trying a set of passwords on a single user's account.</span></span>

<span data-ttu-id="08392-197">**중요 참고** 이미 다단계 인증이 있는 최종 사용자 계정에 대해 무작위 암호 공격을 실행 하면 보고에 해당 계정에 대 한 실패 시도가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-197">**Important Note** running the brute-force password attacks against end user accounts that already have multi-factor authentication, will result in a unsuccessful attempt for those accounts in the reporting.</span></span> <span data-ttu-id="08392-198">이것은 multi-factor authentication이 무작위 암호 공격 으로부터 보호 하기 위해 기본 mechanims 중 하나에 해당 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="08392-198">This is due to multi-factor authentication being one of the primary mechanims to help protect against brute-force password attacks, so is expected.</span></span>

### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="08392-199">무작위 암호 공격을 시뮬레이트하기 위해</span><span class="sxs-lookup"><span data-stu-id="08392-199">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="08392-200">[보안 &amp; 및 준수 센터](https://protection.office.com)에서 **위협 관리** \> **공격 시뮬레이터**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-200">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="08392-201">공격에 대해 의미 있는 캠페인 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-201">Specify a meaningful campaign name for the attack.</span></span>

3. <span data-ttu-id="08392-202">대상 받는 사람을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-202">Specify the target recipient.</span></span> <span data-ttu-id="08392-203">공격이 성공 하려면 대상 받는 사람에 게 Exchange Online 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-203">A targeted recipient must have an Exchange Online mailbox in order for the attack to be successful.</span></span>

4. <span data-ttu-id="08392-204">공격에 사용할 암호 집합을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-204">Specify a set of passwords to use for the attack.</span></span> <span data-ttu-id="08392-205">이렇게 하려면 암호 목록에 텍스트 (.txt) 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-205">To do this, you can use a text (.txt) file for your list of passwords.</span></span> <span data-ttu-id="08392-206">텍스트 파일의 크기는 10mb를 넘을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="08392-206">The text file cannot exceed 10 MB in file size.</span></span> <span data-ttu-id="08392-207">한 줄에 하나씩 암호를 사용 하 고 목록의 마지막 암호 다음에 하드 리턴을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-207">Use one password per line, and make sure to include a hard return after the last password in your list.</span></span>

5. <span data-ttu-id="08392-208">**마침을** 선택 하 여 공격을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-208">Choose **Finish** to launch the attack.</span></span>



<span data-ttu-id="08392-209">[Microsoft 365 로드맵을](https://www.microsoft.com/microsoft-365/roadmap) 방문 하 여 개발 중인 작업, 진행 중인 작업 및 이미 실행 된 작업을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="08392-209">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what's in development, what's rolling out, and what's already launched.</span></span>

## <a name="see-also"></a><span data-ttu-id="08392-210">참고 항목</span><span class="sxs-lookup"><span data-stu-id="08392-210">See also</span></span>

[<span data-ttu-id="08392-211">Office 365 Advanced Threat Protection 서비스 설명</span><span class="sxs-lookup"><span data-stu-id="08392-211">Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[<span data-ttu-id="08392-212">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="08392-212">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
