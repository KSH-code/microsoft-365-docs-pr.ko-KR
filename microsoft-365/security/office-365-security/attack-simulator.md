---
title: Office 365 ATP의 공격 시뮬레이터
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
description: 공격 시뮬레이터를 사용 하 여 Office 365 E5 또는 ATP 계획 2 조직에서 시뮬레이트된 피싱 및 암호 공격을 실행 하면 실제 공격이 비즈니스에 방문 하기 전에 취약 한 사용자를 식별 하는 데 도움이 될 수 있습니다.
ms.openlocfilehash: 5e924ebe43a6d7fd1af460b304e862207baffb61
ms.sourcegitcommit: 9afcc63b1a7e73f6946f67207337f10b71a5d7f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "42612638"
---
# <a name="attack-simulator-in-office-365-atp"></a><span data-ttu-id="6a422-103">Office 365 ATP의 공격 시뮬레이터</span><span class="sxs-lookup"><span data-stu-id="6a422-103">Attack Simulator in Office 365 ATP</span></span>

<span data-ttu-id="6a422-104">Office 365의 Attack 시뮬레이터에서 Advanced Threat Protection 계획 2 (ATP 계획 2)를 사용 하 여 조직에서 현실적 이지만 시뮬레이트된 피싱 및 암호 공격 캠페인을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-104">Attack Simulator in Office 365 Advanced Threat Protection Plan 2 (ATP Plan 2) allows you to run realistic, but simulated phishing and password attack campaigns in your organization.</span></span> <span data-ttu-id="6a422-105">캠페인 결과를 사용 하 여 취약 한 사용자를 식별 하 고 교육할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-105">You can use the results of campaigns to identify and train vulnerable users.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6a422-106">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="6a422-106">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6a422-107">Office 365 보안 & 준수 센터를 열려면로 <https://protection.office.com/>이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-107">To open the Office 365 Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="6a422-108">Attack 시뮬레이터는 **위협 관리** \> **공격 시뮬레이터**에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-108">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span>

  ![위협 관리-공격 시뮬레이터](../../media/ThreatMgmt-AttackSimulator.png)

- <span data-ttu-id="6a422-110">다양 한 Office 365 구독에서 공격 시뮬레이터의 가용성에 대 한 자세한 내용은 [office 365 Advanced Threat Protection 서비스 설명을](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6a422-110">For more information about the availability of Attack Simulator across different Office 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="6a422-111">**조직 관리** 또는 **보안 관리자** 역할 그룹의 구성원 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-111">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="6a422-112">보안 & 준수 센터의 역할 그룹에 대 한 자세한 내용은 [Permissions in The Office 365 Security & 준수 센터](permissions-in-the-security-and-compliance-center.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6a422-112">For more information about role groups in the Security & Compliance Center, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="6a422-113">MFA (multi-factor authentication)를 사용 하 여 공격 시뮬레이터에서 캠페인을 만들고 관리 하도록 계정을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-113">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="6a422-114">자세한 내용은 [다단계 인증 설정을](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6a422-114">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="6a422-115">Exchange Online의 사서함이 있는 사용자에 대해서만 피싱 또는 암호 공격 캠페인을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-115">You can only run phishing or password attack campaigns on users with mailboxes in Exchange Online.</span></span>

- <span data-ttu-id="6a422-116">피싱 캠페인은 30 일 동안 이벤트를 수집 하 고 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-116">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="6a422-117">캠페인을 시작한 후 최대 90 일 동안 역사적 캠페인 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-117">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="6a422-118">Attack 시뮬레이터에 해당 하는 PowerShell cmdlet이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-118">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="6a422-119">스피어 피싱 캠페인</span><span class="sxs-lookup"><span data-stu-id="6a422-119">Spear phishing campaigns</span></span>

<span data-ttu-id="6a422-120">*피싱은* 적법 하거나 신뢰할 수 있는 보낸 사람 으로부터 온 것 처럼 보이는 메시지의 중요 한 정보를 도용 하는 전자 메일 공격에 대 한 일반 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-120">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="6a422-121">*스피어 피싱은* 대상 지정 된 받는 사람에 따라 특별히 조정 된 콘텐츠 (일반적으로 공격자가 받는 사람을 검사 한 후)를 사용 하는 대상 피싱 공격입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-121">*Spear phishing* is a targeted phishing attack that uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="6a422-122">피싱 및 스피어 피싱에 대 한 자세한 내용은 [피싱](https://docs.microsoft.com/windows/security/threat-protection/intelligence/phishing)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="6a422-122">For more information about phishing and spear phishing, see [Phishing](https://docs.microsoft.com/windows/security/threat-protection/intelligence/phishing).</span></span>

<span data-ttu-id="6a422-123">Attack 시뮬레이터에서는 다음과 같은 두 가지 유형의 스피어 피싱 캠페인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-123">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="6a422-124">**스피어 피싱 (자격 증명 수집)**:이 공격은 수신자에 게 메시지의 URL을 클릭 하도록 유도 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-124">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="6a422-125">링크를 클릭 하면 사용자에 게 자격 증명을 입력 하 라는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-125">If they click the link, users are asked to enter their credentials.</span></span> <span data-ttu-id="6a422-126">이러한 경우에는 다음 위치 중 하나로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-126">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="6a422-127">이를 설명 하는 기본 페이지는 테스트 일 뿐 이며 피싱 메시지를 인식 하기 위한 팁을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-127">A default page that explains this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![피싱 링크를 클릭 하 고 해당 자격 증명을 입력 하면 사용자에 게 표시 되는 항목](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="6a422-129">지정 하는 사용자 지정 페이지 (URL)입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-129">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="6a422-130">**스피어 피싱 (첨부 파일)**:이 공격은 받는 사람이 메시지에 있는 .docx 또는 .pdf 첨부 파일을 열도록 유도 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-130">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="6a422-131">첨부 파일은 기본 피싱 링크와 동일한 콘텐츠를 포함 하지만 첫 문장이 "표시 이름\<\>"으로 시작 되며,이 메시지는 사용자가 연 최근 전자 메일 메시지로 나타납니다. "</span><span class="sxs-lookup"><span data-stu-id="6a422-131">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="6a422-132">현재 공격 시뮬레이터의 스피어 피싱 캠페인은 만료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-132">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="6a422-133">스피어 피싱 캠페인 만들기</span><span class="sxs-lookup"><span data-stu-id="6a422-133">Create a spear phishing campaign</span></span>

<span data-ttu-id="6a422-134">모든 스피어 피싱 캠페인의 중요 한 부분은 대상으로 지정 된 받는 사람에 게 전송 되는 전자 메일 메시지의 모양과 느낌입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-134">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="6a422-135">전자 메일 메시지를 만들고 구성 하려면 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-135">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="6a422-136">**기본 제공 전자 메일 서식 파일 사용**: **Giveaway** 및 **급여 업데이트**라는 두 가지 기본 제공 서식 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-136">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="6a422-137">캠페인을 만들고 시작할 때 서식 파일에서 전자 메일 속성의 일부, 전체 또는 일부를 추가로 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-137">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="6a422-138">**재사용 가능한 전자 메일 서식 파일 만들기**: 전자 메일 템플릿을 만들고 저장 한 후 나중에 스피어 피싱 캠페인에서 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-138">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="6a422-139">캠페인을 만들고 시작할 때 서식 파일에서 전자 메일 속성의 일부, 전체 또는 일부를 추가로 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-139">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="6a422-140">**마법사에서 전자 메일 메시지 만들기**: 스피어 피싱 캠페인을 만들고 시작할 때 마법사에서 직접 전자 메일 메시지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-140">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="6a422-141">1 단계 (선택 사항): 사용자 지정 전자 메일 서식 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="6a422-141">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="6a422-142">기본 제공 서식 파일 중 하나를 사용 하거나 마법사에서 직접 전자 메일 메시지를 만들려는 경우이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-142">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="6a422-143">보안 & 준수 센터에서 **위협 관리** \> **공격 시뮬레이터**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-143">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="6a422-144">**공격 시뮬레이션** 페이지의 **스피어 피싱 (자격 증명 수집)** 또는 **스피어 피싱 (첨부 파일)** 섹션에서 **공격 세부 정보**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-144">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="6a422-145">서식 파일을 만드는 위치는 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-145">It doesn't matter where you create the template.</span></span> <span data-ttu-id="6a422-146">서식 파일에서 사용할 수 있는 옵션은 두 가지 유형의 피싱 공격 모두에서 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-146">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="6a422-147">**공격 세부 정보** 페이지가 열리면 **피싱 템플릿** 섹션의 **서식 파일 만들기** 영역에서 **새 서식 파일**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-147">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="6a422-148">**피싱 서식 파일 구성** 마법사가 새 플라이 아웃에서 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-148">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="6a422-149">**시작** 단계에 서식 파일의 고유한 표시 이름을 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-149">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="6a422-150">**전자 메일 세부 정보 구성** 단계에서 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-150">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="6a422-151">**From (이름)**: 메시지 보낸 사람에 게 사용 되는 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-151">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="6a422-152">보낸 사람 **(전자 메일)**: 보낸 사람의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-152">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="6a422-153">**피싱 로그인 서버 URL**: 드롭다운을 클릭 하 고 목록에서 사용 가능한 url 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-153">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="6a422-154">사용자가 클릭 하려고 하는 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-154">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="6a422-155">선택은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-155">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     > <ul><li><span data-ttu-id="6a422-156">모든 Url은 https가 아닌 고의로 http입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-156">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="6a422-157">URL 신뢰도 서비스가 이러한 Url 중 하나 이상을 안전 하지 않은 것으로 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-157">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="6a422-158">피싱 캠페인에서 URL을 사용 하기 전에 지원 되는 웹 브라우저에서 URL의 가용성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-158">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li></ul>

   - <span data-ttu-id="6a422-159">**사용자 지정 랜딩 페이지 URL**: 사용자가 피싱 링크를 클릭 하 고 해당 자격 증명을 입력할 수 있는 선택적 랜딩 페이지를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-159">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="6a422-160">이 링크는 기본 랜딩 페이지를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-160">This link replaces the default landing page.</span></span> <span data-ttu-id="6a422-161">예를 들어 내부 인식 교육이 있는 경우 여기에서 해당 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-161">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="6a422-162">**범주**: 현재이 설정은 사용 되지 않습니다 (입력 한 내용은 무시 됨).</span><span class="sxs-lookup"><span data-stu-id="6a422-162">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="6a422-163">**제목**: 전자 메일 메시지의 **제목** 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-163">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="6a422-164">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-164">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6a422-165">**전자 메일 작성** 단계에서 전자 메일 메시지의 메시지 본문을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-165">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="6a422-166">**전자 메일** 탭 (리치 html 편집기) 또는 **원본** 탭 (원시 HTML 코드)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-166">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="6a422-167">HTML 서식 지정은 필요한 경우에는 단순 하거나 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-167">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="6a422-168">이미지와 텍스트를 삽입 하 여 받는 사람의 전자 메일 클라이언트에서 메시지의 believability을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-168">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="6a422-169">`${username}`받는 사람의 이름을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-169">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="6a422-170">`${loginserverurl}`이전 단계의 **피싱 로그인 서버 URL** 값을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-170">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="6a422-171">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-171">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="6a422-172">**확인** 단계에서 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-172">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="6a422-173">2 단계: 스피어 피싱 캠페인 만들기 및 시작</span><span class="sxs-lookup"><span data-stu-id="6a422-173">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="6a422-174">보안 & 준수 센터에서 **위협 관리** \> **공격 시뮬레이터**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-174">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="6a422-175">**공격 시뮬레이션** 페이지에서 만들려는 캠페인 유형에 따라 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-175">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="6a422-176">**스피어 피싱 (자격 증명 수집)** 섹션에서 **공격 시작** 을 클릭 하거나 **공격 정보** \> **시작 공격**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-176">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="6a422-177">**스피어 피싱 (첨부 파일)** 섹션에서 **공격 시작** 을 클릭 하거나 **공격 정보** \> **시작 공격**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-177">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="6a422-178">**피싱 공격 구성** 마법사가 새 플라이 아웃으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-178">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="6a422-179">**시작** 단계에서 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-179">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="6a422-180">**이름** 상자에 캠페인의 고유한 표시 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-180">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="6a422-181">마법사에서 나중에 전자 메일 메시지를 만들기 때문에 **서식 파일 사용**을 클릭 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="6a422-181">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="6a422-182">**서식 파일 사용** 을 클릭 하 고 기본 제공 또는 사용자 지정 전자 메일 서식 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-182">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="6a422-183">서식 파일을 선택한 후에는 **이름** 상자에 서식 파일이 자동으로 입력 되지만 이름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-183">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![피싱 시작 페이지](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="6a422-185">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-185">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="6a422-186">**대상 받는 사람** 단계에서 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-186">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="6a422-187">**주소록** 을 클릭 하 여 캠페인에 대 한 받는 사람 (사용자 또는 그룹)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-187">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="6a422-188">각각의 대상 지정 받는 사람에 게 Exchange Online 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-188">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="6a422-189">검색 조건을 입력 하지 않고 **필터** 및 **적용** 을 클릭 하면 모든 받는 사람이 반환 되 고 캠페인에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-189">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="6a422-190">**파일** 가져오기를 클릭 하 여 CSV (쉼표로 구분 된 값) 또는 전자 메일 주소에 대 한 행 구분 파일 **을 가져옵니다.**</span><span class="sxs-lookup"><span data-stu-id="6a422-190">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="6a422-191">각 줄에는 받는 사람의 전자 메일 주소가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-191">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="6a422-192">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-192">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6a422-193">**전자 메일 세부 정보 구성** 단계에서 다음 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-193">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="6a422-194">**시작** 단계에서 템플릿을 선택한 경우 이러한 값의 대부분은 이미 구성 되어 있지만 변경할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-194">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="6a422-195">**From (이름)**: 메시지 보낸 사람에 게 사용 되는 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-195">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="6a422-196">보낸 사람 **(전자 메일)**: 보낸 사람의 전자 메일 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-196">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="6a422-197">조직의 전자 메일 도메인에서 실제 또는 가짜 전자 메일 주소를 입력 하거나, 실제 또는 가짜 외부 전자 메일 주소를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-197">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="6a422-198">조직의 유효한 보낸 사람 전자 메일 주소가 실제로 받는 사람의 전자 메일 클라이언트에서 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-198">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="6a422-199">**피싱 로그인 서버 URL**: 드롭다운을 클릭 하 고 목록에서 사용 가능한 url 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-199">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="6a422-200">사용자가 클릭 하려고 하는 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-200">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="6a422-201">선택은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-201">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     > <ul><li><span data-ttu-id="6a422-202">모든 Url은 https가 아닌 고의로 http입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-202">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="6a422-203">URL 신뢰도 서비스가 이러한 Url 중 하나 이상을 안전 하지 않은 것으로 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-203">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="6a422-204">피싱 캠페인에서 URL을 사용 하기 전에 지원 되는 웹 브라우저에서 URL의 가용성을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-204">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li><li><span data-ttu-id="6a422-205">URL을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-205">You are required to select a URL.</span></span> <span data-ttu-id="6a422-206">**스피어 피싱 (첨부 파일)** 캠페인의 경우 다음 단계에서 메시지 본문의 링크를 제거할 수 있습니다 (그렇지 않으면 메시지에 링크 **와** 첨부 파일이 모두 포함 됨).</span><span class="sxs-lookup"><span data-stu-id="6a422-206">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span></li></ul>

   - <span data-ttu-id="6a422-207">**첨부 파일 형식**:이 설정은 **스피어 피싱 (첨부 파일)** 캠페인 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-207">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="6a422-208">드롭다운을 클릭 하 고를 선택 **합니다. .DOCX** 또는 \*\*. \*\*목록에서 PDF를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-208">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="6a422-209">**첨부 파일 이름**:이 설정은 **스피어 피싱 (첨부 파일)** 캠페인 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-209">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="6a422-210">.Docx 또는 .pdf 첨부 파일의 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-210">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="6a422-211">**사용자 지정 랜딩 페이지 URL**: 사용자가 피싱 링크를 클릭 하 고 해당 자격 증명을 입력할 수 있는 선택적 랜딩 페이지를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-211">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="6a422-212">이 링크는 기본 랜딩 페이지를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-212">This link replaces the default landing page.</span></span> <span data-ttu-id="6a422-213">예를 들어 내부 인식 교육이 있는 경우 여기에서 해당 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-213">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="6a422-214">**제목**: 전자 메일 메시지의 **제목** 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-214">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="6a422-215">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-215">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6a422-216">**전자 메일 작성** 단계에서 전자 메일 메시지의 메시지 본문을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-216">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="6a422-217">**시작** 단계에서 템플릿을 선택한 경우 메시지 본문이 이미 구성 되어 있지만 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-217">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="6a422-218">**전자 메일** 탭 (리치 html 편집기) 또는 **원본** 탭 (원시 HTML 코드)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-218">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="6a422-219">HTML 서식 지정은 필요한 경우에는 단순 하거나 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-219">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="6a422-220">이미지와 텍스트를 삽입 하 여 받는 사람의 전자 메일 클라이언트에서 메시지의 believability을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-220">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="6a422-221">`${username}`받는 사람의 이름을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-221">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="6a422-222">`${loginserverurl}`**피싱 로그인 서버 URL** 값을 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-222">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="6a422-223">**스피어 피싱 (첨부 파일)** 캠페인의 경우 메시지 본문에서 링크를 제거 해야 합니다 (그렇지 않으면 메시지에 링크 **와** 첨부 파일이 모두 포함 되며 첨부 파일 캠페인에서는 링크 클릭이 추적 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="6a422-223">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![전자 메일 본문 작성](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="6a422-225">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-225">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="6a422-226">**확인** 단계에서 **마침을** 클릭 하 여 캠페인을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-226">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="6a422-227">피싱 메시지는 대상이 지정 된 받는 사람에 게 배달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-227">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="6a422-228">암호 공격 캠페인</span><span class="sxs-lookup"><span data-stu-id="6a422-228">Password attack campaigns</span></span>

<span data-ttu-id="6a422-229">*암호 공격은* 대개 공격자가 하나 이상의 유효한 사용자 계정을 식별 한 후 조직의 사용자 계정에 대 한 암호를 추측 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-229">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="6a422-230">Attack 시뮬레이터에서는 사용자 암호의 복잡도를 테스트 하기 위해 다음과 같은 두 가지 유형의 암호 공격 캠페인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-230">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="6a422-231">**무작위 암호 (사전 공격)**: *무작위 강제*\* 또는 *사전* 공격에서는 사용자 계정 중 하나에 대 한 암호 (대부분의 암호는 여러 개)를 사용할 수 있는 대규모 사전 파일을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-231">**Brute force password (dictionary attack)**: A *brute force*\* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="6a422-232">잘못 된 암호 잠금 해제로 인해 무작위 암호 공격을 방지 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-232">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="6a422-233">사전 공격의 경우에는 하나 이상의 암호를 지정 하 여 (수동으로 입력 하거나 업로드 한 파일에) 시도할 수 있으며, 하나 또는 여러 명의 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-233">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="6a422-234">**암호 분무 공격**: *암호 분무* 공격에서는 사용자 계정 목록 (여러 계정에 대해 암호 하나씩)에 대해 신중 하 게 동일한 암호를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-234">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="6a422-235">암호 분무 공격은 무작위 암호 공격 보다 검색 하기가 더 어렵게 됩니다 (공격자가 사용자의 잘못 된 암호 잠금을 통과 하는 위험 없이 수십 또는 수백 개의 계정에서 암호를 한 번에 입력 해야 하는 경우에는 성공 확률이 증가 함).</span><span class="sxs-lookup"><span data-stu-id="6a422-235">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="6a422-236">암호 분무 공격의 경우 시도할 암호를 하나만 지정할 수 있으며, 한 명 또는 여러 명의 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-236">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="6a422-237">Attack 시뮬레이터의 암호 공격은 사용자 이름 및 암호 기본 인증 요청을 끝점에 전달 하므로 다른 인증 방법 (AD FS, 암호 해시 동기화, 통과, 공동 페더레이션 등) 에서도 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-237">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="6a422-238">MFA를 사용 하도록 설정 된 사용자의 경우 암호 공격이 실제 암호를 시도 하더라도 항상 실패로 등록 됩니다 (즉, MFA 사용자는 해당 캠페인의 **성공한 시도** 횟수에 표시 되지 않음).</span><span class="sxs-lookup"><span data-stu-id="6a422-238">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="6a422-239">이는 예상 되는 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-239">This is the expected result.</span></span> <span data-ttu-id="6a422-240">MFA는 암호 공격 으로부터 보호 하는 기본 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-240">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="6a422-241">암호 공격 캠페인 만들기 및 시작</span><span class="sxs-lookup"><span data-stu-id="6a422-241">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="6a422-242">보안 & 준수 센터에서 **위협 관리** \> **공격 시뮬레이터**로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-242">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="6a422-243">**공격 시뮬레이션** 페이지에서 만들려는 캠페인 유형에 따라 다음 중 하나를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-243">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="6a422-244">**무작위 암호 (사전 공격)** 섹션에서 **공격 시작** 을 클릭 하거나 **공격 정보** \> **시작 공격**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-244">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="6a422-245">**암호 분무 공격** 섹션에서 **공격 시작** 을 클릭 하거나 **공격 정보** \> **시작 공격**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-245">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="6a422-246">**암호 공격 구성** 마법사가 새 플라이 아웃으로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-246">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="6a422-247">**시작** 단계에서 캠페인의 고유한 표시 이름을 입력 하 고 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-247">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="6a422-248">**대상 사용자** 단계에서 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-248">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="6a422-249">**주소록** 을 클릭 하 여 캠페인에 대 한 받는 사람 (사용자 또는 그룹)을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-249">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="6a422-250">각각의 대상 지정 받는 사람에 게 Exchange Online 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-250">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="6a422-251">검색 조건을 입력 하지 않고 **필터** 및 **적용** 을 클릭 하면 모든 받는 사람이 반환 되 고 캠페인에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-251">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="6a422-252">**파일** 가져오기를 클릭 하 여 CSV (쉼표로 구분 된 값) 또는 전자 메일 주소에 대 한 행 구분 파일 **을 가져옵니다.**</span><span class="sxs-lookup"><span data-stu-id="6a422-252">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="6a422-253">각 줄에는 받는 사람의 전자 메일 주소가 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-253">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="6a422-254">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-254">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6a422-255">**공격 설정 선택** 단계에서 캠페인 유형에 따라 수행할 작업을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-255">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="6a422-256">**무작위 암호 (사전 공격)**: 다음 단계 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-256">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="6a422-257">**암호를 수동으로 입력**합니다. **암호를 추가 하려면 Enter 키를 누릅니다** 상자에 암호를 입력 한 다음 enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-257">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="6a422-258">필요한 횟수만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-258">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="6a422-259">**사전 파일에서 암호 업로드**: **업로드** 를 클릭 하 여 각 줄에 하나의 암호를 포함 하는 기존 텍스트 파일을 가져오고 마지막 줄에는 빈 행을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-259">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="6a422-260">텍스트 파일의 크기는 10mb이 하 여야 하며, 3만 개 이하의 암호를 포함할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-260">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="6a422-261">**암호 분무 공격**: **공격 상자에 사용할 암호** 에 암호를 하나 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-261">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="6a422-262">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-262">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6a422-263">**확인** 단계에서 **마침을** 클릭 하 여 캠페인을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-263">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="6a422-264">지정한 암호가 지정한 사용자에 게 시도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-264">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="6a422-265">캠페인 결과 보기</span><span class="sxs-lookup"><span data-stu-id="6a422-265">View campaign results</span></span>

<span data-ttu-id="6a422-266">캠페인을 시작한 후에는 기본 **시뮬레이트 공격** 페이지에서 진행률 및 결과를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-266">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="6a422-267">활성 캠페인은 상태 표시줄, 완료 된 백분율 값 및 "(전체 사용자)" 수 "개수를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-267">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="6a422-268">**새로 고침** 단추를 클릭 하면 활성 캠페인의 진행률이 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-268">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="6a422-269">또한 **종료** 를 클릭 하 여 활성 캠페인을 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-269">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="6a422-270">캠페인이 완료 되 면 상태가 " **공격 완료 됨**"으로 변경 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-270">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="6a422-271">다음 작업 중 하나를 수행 하 여 캠페인의 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-271">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="6a422-272">주 **시뮬레이트 공격** 페이지에서 캠페인 이름 아래에 있는 **보고서 보기** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-272">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="6a422-273">주 **시뮬레이트 공격** 페이지에서 공격 유형에 대 한 섹션에서 **공격 세부 정보** 를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-273">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="6a422-274">**공격 정보** 페이지가 열리면 **공격 기록** 섹션에서 캠페인을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-274">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="6a422-275">이전 작업 중 하나를 수행 하면 **Attack details**라는 페이지가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-275">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="6a422-276">각 캠페인 유형에 대해이 페이지에서 제공 되는 정보는 다음 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-276">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="6a422-277">스피어 피싱 (자격 증명 수집) 캠페인 결과</span><span class="sxs-lookup"><span data-stu-id="6a422-277">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="6a422-278">각 캠페인의 **공격 세부 정보** 페이지에서는 다음 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-278">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="6a422-279">캠페인의 기간 (시작 날짜/시간 및 종료 날짜/시간)입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-279">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="6a422-280">**총 대상 사용자**</span><span class="sxs-lookup"><span data-stu-id="6a422-280">**Total users targeted**</span></span>

- <span data-ttu-id="6a422-281">**성공**: 링크를 클릭 **하 고** 자격 증명 (*사용자 이름 및* 암호 값)을 입력 한 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-281">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="6a422-282">**전체 성공률**:**총 사용자**수에 대해 **성공한 시도** / 를 통해 계산 되는 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-282">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="6a422-283">**고속 클릭**: 처음 사용자가 캠페인을 시작한 후 링크를 클릭 하는 데 소요 되는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-283">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="6a422-284">**Average 클릭**: 모든 사용자가 링크를 클릭 하는 데 걸린 시간 합계를 링크를 클릭 한 사용자 수로 나눕니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-284">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="6a422-285">**성공률**: (링크를 클릭 한 사용자 수)/ **총 대상 사용자**에 게 계산 되는 백분율을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-285">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="6a422-286">**가장 빠른 자격 증명**: 캠페인을 시작한 후 첫 번째 사용자가 자격 증명을 입력 하는 데 소요 되는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-286">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="6a422-287">**평균 자격 증명**: 모든 사용자가 자격 증명을 입력 하는 데 걸린 시간 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-287">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="6a422-288">**자격 증명 성공률**: (자격 증명을 입력 한 사용자 수)/ **총 대상 사용자**를 기준으로 계산 되는 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-288">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="6a422-289">**클릭 한 링크** 와 하루 당 제공 되는 **자격 증명** 수를 보여 주는 막대 그래프입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-289">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="6a422-290">**클릭 한 링크**, **제공 된 자격 증명**및 캠페인에 대 한 **백분율을** 보여주는 원 그래프입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-290">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="6a422-291">**손상 된 사용자** 섹션에는 링크를 클릭 한 사용자에 대 한 자세한 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-291">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="6a422-292">사용자의 전자 메일 주소</span><span class="sxs-lookup"><span data-stu-id="6a422-292">The user's email address</span></span>

  - <span data-ttu-id="6a422-293">링크를 클릭 한 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-293">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="6a422-294">클라이언트 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-294">The client IP address.</span></span>

  - <span data-ttu-id="6a422-295">사용자 버전의 Windows 및 웹 브라우저에 대 한 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-295">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="6a422-296">**내보내기를** 클릭 하 여 결과를 CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-296">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="6a422-297">스피어 피싱 (첨부 파일) 캠페인 결과</span><span class="sxs-lookup"><span data-stu-id="6a422-297">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="6a422-298">각 캠페인의 **공격 세부 정보** 페이지에서는 다음 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-298">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="6a422-299">캠페인의 기간 (시작 날짜/시간 및 종료 날짜/시간)입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-299">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="6a422-300">**총 대상 사용자**</span><span class="sxs-lookup"><span data-stu-id="6a422-300">**Total users targeted**</span></span>

- <span data-ttu-id="6a422-301">**성공한 시도**: 첨부 파일을 열거나 다운로드 한 후 연 사용자 수 (미리 보기에서 계산 되지 않음)입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-301">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="6a422-302">**전체 성공률**:**총 사용자**수에 대해 **성공한 시도** / 를 통해 계산 되는 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-302">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="6a422-303">**가장 빠른 첨부 파일 열기 시간**: 캠페인을 시작한 후 첫 번째 사용자가 첨부 파일을 여는 데 소요 되는 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-303">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="6a422-304">**평균 첨부 파일 열기 시간**: 모든 사용자가 첨부 파일을 여는 데 걸린 시간 합계입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-304">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="6a422-305">**첨부 파일 열기 성공률**: (첨부 파일을 연 사용자 수)/ **총 대상 사용자**를 기준으로 계산 되는 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-305">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="6a422-306">무작위 암호 (사전 공격) 캠페인 결과</span><span class="sxs-lookup"><span data-stu-id="6a422-306">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="6a422-307">각 캠페인의 **공격 세부 정보** 페이지에서는 다음 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-307">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="6a422-308">캠페인의 기간 (시작 날짜/시간 및 종료 날짜/시간)입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-308">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="6a422-309">**총 대상 사용자**</span><span class="sxs-lookup"><span data-stu-id="6a422-309">**Total users targeted**</span></span>

- <span data-ttu-id="6a422-310">**성공한 시도**: 지정 된 암호 중 하나를 사용 하는 것으로 확인 된 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-310">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="6a422-311">**전체 성공률**:**총 사용자**수에 대해 **성공한 시도** / 를 통해 계산 되는 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-311">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="6a422-312">**손상 된 사용자** 섹션에는 영향을 받는 사용자의 전자 메일 주소가 나열 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-312">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="6a422-313">**내보내기를** 클릭 하 여 결과를 CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-313">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="6a422-314">암호 분무 공격 캠페인 결과</span><span class="sxs-lookup"><span data-stu-id="6a422-314">Password spray attack campaign results</span></span>

<span data-ttu-id="6a422-315">각 캠페인의 **공격 세부 정보** 페이지에서는 다음 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-315">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="6a422-316">캠페인의 기간 (시작 날짜/시간 및 종료 날짜/시간)입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-316">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="6a422-317">**총 대상 사용자**</span><span class="sxs-lookup"><span data-stu-id="6a422-317">**Total users targeted**</span></span>

- <span data-ttu-id="6a422-318">**성공**: 지정 된 암호를 사용 하 여 검색 된 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-318">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="6a422-319">**전체 성공률**:**총 사용자**수에 대해 **성공한 시도** / 를 통해 계산 되는 백분율입니다.</span><span class="sxs-lookup"><span data-stu-id="6a422-319">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
