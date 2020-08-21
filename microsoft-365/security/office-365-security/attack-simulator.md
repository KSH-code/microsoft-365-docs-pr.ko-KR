---
title: ATP의 공격 시뮬레이터
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 관리자는 공격 시뮬레이터를 사용하여 Microsoft 365 E5 또는 ATP 플랜 2 조직에서 시뮬레이트된 피싱 및 암호 공격을 실행하는 방법을 학습할 수 있습니다.
ms.openlocfilehash: 017376d8002811398fe3ce2d94f7c207cd718a78
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825836"
---
# <a name="attack-simulator-in-atp"></a><span data-ttu-id="26226-103">ATP의 공격 시뮬레이터</span><span class="sxs-lookup"><span data-stu-id="26226-103">Attack Simulator in ATP</span></span>

<span data-ttu-id="26226-104">조직에 위협 조사 및 응답 기능을 포함한 Office 365 ATP(Advanced Threat Protection) 계획 2가 [있는](office-365-ti.md)경우 보안 & 규정 준수 센터에서 공격 시뮬레이터를 사용하여 조직에서 실제 공격 시나리오를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-104">If your organization has Office 365 Advanced Threat Protection (ATP) Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="26226-105">시뮬레이션된 공격은 실수로 관한 공격이 수월한 줄에 영향을 미치기 전에 취약한 사용자를 식별하고 찾는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="26226-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="26226-106">이 문서를 읽어 자세히 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="26226-106">Read this article to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="26226-107">시작하기 전에 알아야 할 사항은 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="26226-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="26226-108">보안 및 준수 센터를 열려면 <https://protection.office.com/>로 이동하세요.</span><span class="sxs-lookup"><span data-stu-id="26226-108">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="26226-109">공격 시뮬레이터는 위협 관리 **공격** \> **시뮬레이터에서 사용할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="26226-109">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="26226-110">공격 시뮬레이터로 직접 이동하여 <https://protection.office.com/attacksimulator> 열기</span><span class="sxs-lookup"><span data-stu-id="26226-110">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="26226-111">여러 Microsoft 365 구독에서의 공격 시뮬레이터의 가용성에 대한 자세한 내용은 [Office 365 Advanced Threat Protection 서비스 설명을 참조하세요.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="26226-111">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="26226-112">Organization Management 또는 Security Administrator 역할 **그룹의** **구성원이어야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-112">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="26226-113">보안 및 규정 준수 센터의 역할 그룹에 대한 자세한 내용은 [보안 및 규정 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="26226-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="26226-114">다단계 인증(MFA)에 대해 계정을 구성하여 공격 시뮬레이터에서 캠페인을 만들고 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-114">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="26226-115">관련 지침은 다단계 [인증 설정을 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)</span><span class="sxs-lookup"><span data-stu-id="26226-115">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="26226-116">피싱 캠페인은 30일 동안 이벤트를 수집 및 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-116">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="26226-117">제공된 업데이트임에 따라 캠페인을 시작한 후 최대 90일 동안 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-117">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="26226-118">공격 시뮬레이터에 해당하는 PowerShell cmdlet은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-118">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="26226-119">스피어 피싱 캠페인</span><span class="sxs-lookup"><span data-stu-id="26226-119">Spear phishing campaigns</span></span>

<span data-ttu-id="26226-120">*피싱은* 합법적이거나 신뢰할 수 있는 보낸 사람이 보내는 메시지에 중요한 정보를 도용하라고 시도하는 전자 메일 공격의 일반적인 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-120">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="26226-121">*스피어 피싱은* 중심이 맞춤되는 사용자 지정된 콘텐츠(일반적으로 공격자가 받는 사람을 수정한 후)에 맞게 맞게 정렬되고 사용자 지정된 콘텐츠를 사용하는 을 목표로 하는 피싱 공격입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-121">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="26226-122">공격 시뮬레이터에서는 두 가지 유형의 스피어 피싱 캠페인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-122">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="26226-123">**스피어 피싱(자격 증명 은은 결제):** 공격은 받는 사람을 초대하여 메시지에서 URL을 클릭하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-123">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="26226-124">링크를 클릭하면 자격 증명을 입력하라는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="26226-124">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="26226-125">이렇게 되면 다음 위치 중 하나로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="26226-125">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="26226-126">이 작업을 테스트에 사용한 테스트로 설명하고 피싱 메시지를 인식하기 위한 팁을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-126">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![사용자가 피싱 링크를 클릭하면 해당 자격 증명을 입력하면 나타나는 항목](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="26226-128">지정하는 사용자 지정 페이지(URL)입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-128">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="26226-129">**스피어 피싱(첨부 파일):** 공격자는 받는 사람이 메시지에 .docx 또는 .pdf 첨부 파일을 열도록 유도합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-129">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="26226-130">첨부 파일에 기본 피싱 링크의 내용과 동일한 내용이 있지만 첫 번째 문장은 "을 연 최근 전자 메일 메시지로 \<Display Name\> 표시됩니다.."로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-130">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="26226-131">현재 공격 시뮬레이터의 스피어 피싱 캠페인은 만료되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-131">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="26226-132">스피어 피싱 캠페인 만들기</span><span class="sxs-lookup"><span data-stu-id="26226-132">Create a spear phishing campaign</span></span>

<span data-ttu-id="26226-133">스피어 피싱 캠페인의 중요한 부분은 대상이 지정된 받는 사람에게 보내지는 전자 메일 메시지의 모양과 경사입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-133">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="26226-134">전자 메일 메시지를 만들고 구성하려면 다음 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-134">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="26226-135">**기본 제공 전자 메일 템플릿 사용: 기본**제공된 두 가지 서식 파일 사용: **급진화** 및 **급지 지급**업데이트.</span><span class="sxs-lookup"><span data-stu-id="26226-135">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="26226-136">캠페인을 만들고 시작할 때 템플릿에서 전자 메일 속성의 일부 또는 전부 또는 일부를 더 사용자 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-136">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="26226-137">**다시 사용할 수 있는 전자 메일 템플릿**만들기 : 전자 메일 템플릿을 만들고 저장한 후 이후 피싱 캠페인에서 이 템플릿을 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-137">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="26226-138">캠페인을 만들고 시작할 때 템플릿에서 전자 메일 속성의 일부 또는 전부 또는 일부를 더 사용자 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-138">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="26226-139">**마법사에서 메일 메시지를 만듭니다.** 마법사에서 메일 메시지를 직접 만들고 스피어 피싱 캠페인을 만들고 시작할 때 를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-139">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="26226-140">1단계(선택 사항): 사용자 지정 전자 메일 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="26226-140">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="26226-141">기본 제공 템플릿 중 하나를 사용하거나 마법사에서 직접 메일 메시지를 만들려는 경우에는 이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-141">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="26226-142">보안 그룹 의& 규정 준수 센터에서 **위협 관리** \> **공격 시뮬레이터로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="26226-142">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="26226-143">공격 **시뮬레이트 페이지의** **스피어 피싱(자격 증명 정보 가리키기)** 또는 **스피어 피싱(첨부 파일)** 섹션에서 공격 세부 정보를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="26226-143">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="26226-144">템플릿을 만드는 위치에 는 상주하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-144">It doesn't matter where you create the template.</span></span> <span data-ttu-id="26226-145">서식 파일에서 사용 가능한 옵션은 두 가지 유형의 피싱 공격에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-145">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="26226-146">**열리는 공격** 세부 정보 페이지의 **피싱 템플릿** 섹션에서 서식 파일 만들기 영역에서 새 **템플릿을** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="26226-146">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="26226-147">피싱 **템플릿 구성 마법사가 새** 플라이아웃에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-147">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="26226-148">시작 **단계에서** 템플릿의 고유한 표시 이름을 입력하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="26226-148">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="26226-149">전자 메일 **세부 정보 구성 단계에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-149">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="26226-150">**발신자(이름):** 메시지 보낸 사람을 위한 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-150">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="26226-151">**From (Email)**: The sender's email address.</span><span class="sxs-lookup"><span data-stu-id="26226-151">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="26226-152">**피싱 로그인 서버 URL:** 드롭다운을 클릭하고 목록에서 사용 가능한 URL 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-152">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="26226-153">이 URL은 사용자가 클릭하는 데 일시적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="26226-153">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="26226-154">선택은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-154">The choices are:</span></span>

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
     >
     > - <span data-ttu-id="26226-155">모든 URL은 의도적으로 http가 아주 http입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-155">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="26226-156">URL 신뢰도 서비스는 이러한 URL 중 하나 이상을 안전하지 않은 URL로 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-156">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="26226-157">피싱 캠페인에서 URL을 사용하기 전에 지원되는 웹 브라우저에서 URL의 가용성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-157">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="26226-158">**사용자 지정 방문 페이지 URL:** 피싱 링크를 클릭하고 해당 자격 증명을 입력할 경우 사용자가 취할 사항이 있는 방문 페이지를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-158">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="26226-159">이 링크는 기본 랜딩 페이지를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-159">This link replaces the default landing page.</span></span> <span data-ttu-id="26226-160">예를 들어 내부 인식 교육이 있는 경우 여기에서 해당 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-160">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="26226-161">**범주:** 현재 이 설정은 사용되지 않습니다(입력한 모든 항목은 무시됩니다).</span><span class="sxs-lookup"><span data-stu-id="26226-161">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="26226-162">**제목:** 전자 **메일 메시지의** 제목 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-162">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="26226-163">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-163">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="26226-164">전자 메일 **작성 단계에서 전자 메일** 메시지의 메시지 본문을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="26226-164">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="26226-165">전자 메일 **탭(풍부한** HTML 편집기) **Source** 또는 원본 탭(원시 HTML 코드)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-165">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="26226-166">HTML 형식은 필요할 때만 간단할 수도 있고 복잡할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-166">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="26226-167">이미지와 텍스트를 삽입하여 받는 사람의 전자 메일 클라이언트에서 메시지의 안정성을 향상시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-167">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="26226-168">`${username}` 받는 사람 이름을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-168">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="26226-169">`${loginserverurl}` 이전 **단계의 피싱 로그인 서버 URL 값을** 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-169">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="26226-170">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-170">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="26226-171">확인 단계에서 **마침을** **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="26226-171">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="26226-172">2단계: 스피어 피싱 캠페인 만들기 및 시작</span><span class="sxs-lookup"><span data-stu-id="26226-172">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="26226-173">보안 그룹 의& 규정 준수 센터에서 **위협 관리** \> **공격 시뮬레이터로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="26226-173">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="26226-174">공격 **시뮬레이트** 페이지에서, 만들고자 하는 캠페인의 유형에 따라 다음 선택 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-174">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="26226-175">**스피어 피싱(자격 증명 Harvest)** 섹션에서 공격 **실행을 클릭하거나 공격 세부** 정보 실행 **Attack Details** \> **공격을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="26226-175">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="26226-176">**스피어 피싱(첨부 파일) 섹션에서** 공격 실행을 클릭하거나 **공격 세부** 정보 **실행을** \> **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="26226-176">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="26226-177">피싱 **공격 구성 마법사가 새** 플라이아웃에서 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-177">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="26226-178">시작 **단계에서** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-178">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="26226-179">이름 **상자에** 캠페인의 고유한 표시 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-179">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="26226-180">나중에 마법사에서 **전자 메일 메시지를**만들므로 템플릿 사용을 클릭하지 마합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-180">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="26226-181">서식 **파일 사용을** 클릭하고 기본 제공 또는 사용자 지정 전자 메일 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-181">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="26226-182">서식 파일을 선택한 다음에는 **템플릿을 기여하여** 이름 상자가 자동으로 채워지지만 이름을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-182">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![피싱 시작 페이지](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="26226-184">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-184">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="26226-185">대상 받는 **사람 단계에서** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-185">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="26226-186">주소록을 **클릭하여** 캠페인의 받는 사람(사용자 또는 그룹)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-186">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="26226-187">대상이 지정된 각 받는 사람은 Exchange Online 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-187">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="26226-188">검색 조건을 **입력하지 않고 필터를** 적용하고 적용을 클릭하면 모든 받는 사람이 반환되며 캠페인에 추가됩니다. **Filter**</span><span class="sxs-lookup"><span data-stu-id="26226-188">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="26226-189">가져오기를 클릭한 **다음 가져오기를** 클릭하여 쉼표로 구분된 값(CSV) 또는 줄으로 구분된 전자 메일 주소 파일을 가져옵니다. **Import**</span><span class="sxs-lookup"><span data-stu-id="26226-189">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="26226-190">각 줄에는 받는 사람의 전자 메일 주소가 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-190">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="26226-191">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-191">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="26226-192">전자 메일 **세부 정보 구성 단계에서** 다음 설정을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-192">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="26226-193">시작 단계에서 템플릿을 선택한 **경우** 이러한 값 대부분은 이미 구성되어 있지만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-193">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="26226-194">**발신자(이름):** 메시지 보낸 사람을 위한 표시 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-194">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="26226-195">**From (Email)**: The sender's email address.</span><span class="sxs-lookup"><span data-stu-id="26226-195">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="26226-196">조직의 전자 메일 도메인에서 가상 또는 위키 전자 메일 주소를 입력하거나 실시간 또는 위키 외부 전자 메일 주소를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-196">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="26226-197">조직에서 보낸 유효한 보낸 사람 전자 메일 주소는 받는 사람의 전자 메일 클라이언트에서 실제로 확인됩니다.</span><span class="sxs-lookup"><span data-stu-id="26226-197">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="26226-198">**피싱 로그인 서버 URL:** 드롭다운을 클릭하고 목록에서 사용 가능한 URL 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-198">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="26226-199">이 URL은 사용자가 클릭하는 데 일시적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="26226-199">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="26226-200">선택은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-200">The choices are:</span></span>

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
     >
     > - <span data-ttu-id="26226-201">모든 URL은 의도적으로 http가 아주 http입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-201">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="26226-202">URL 신뢰도 서비스는 이러한 URL 중 하나 이상을 안전하지 않은 URL로 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-202">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="26226-203">피싱 캠페인에서 URL을 사용하기 전에 지원되는 웹 브라우저에서 URL의 가용성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-203">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="26226-204">URL을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-204">You are required to select a URL.</span></span> <span data-ttu-id="26226-205">**스피어 피싱(첨부 파일)** 캠페인의 경우 다음 단계(그렇지 않으면 메시지에 링크와 첨부 파일이 모두 포함됨)에서 메시지 본문에서 **링크를 제거할** 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-205">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="26226-206">**첨부 파일 형식:** 이 설정은 **스피어 피싱(첨부 파일) 캠페인에서만** 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-206">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="26226-207">드롭다운을 클릭하고 **선택합니다. DOCX** **또는 . 목록의 PDF입니다.**</span><span class="sxs-lookup"><span data-stu-id="26226-207">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="26226-208">**첨부 파일 이름:** 이 설정은 **스피어 피싱(첨부 파일) 캠페인에서만** 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-208">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="26226-209">.docx 또는 .pdf 첨부 파일의 파일 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-209">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="26226-210">**사용자 지정 방문 페이지 URL:** 피싱 링크를 클릭하고 해당 자격 증명을 입력할 경우 사용자가 취할 사항이 있는 방문 페이지를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-210">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="26226-211">이 링크는 기본 랜딩 페이지를 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-211">This link replaces the default landing page.</span></span> <span data-ttu-id="26226-212">예를 들어 내부 인식 교육이 있는 경우 여기에서 해당 URL을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-212">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="26226-213">**제목:** 전자 **메일 메시지의** 제목 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-213">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="26226-214">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-214">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="26226-215">전자 메일 **작성 단계에서 전자 메일** 메시지의 메시지 본문을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="26226-215">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="26226-216">시작 단계에서 서식 파일을 **선택한** 경우 메시지 본문이 이미 구성되어 있지만 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-216">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="26226-217">전자 메일 **탭(풍부한** HTML 편집기) **Source** 또는 원본 탭(원시 HTML 코드)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-217">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="26226-218">HTML 형식은 필요할 때만 간단할 수도 있고 복잡할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-218">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="26226-219">이미지와 텍스트를 삽입하여 받는 사람의 전자 메일 클라이언트에서 메시지의 안정성을 향상시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-219">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="26226-220">`${username}` 받는 사람 이름을 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-220">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="26226-221">`${loginserverurl}`피싱 **로그인 서버 URL 값을 삽입합니다.**</span><span class="sxs-lookup"><span data-stu-id="26226-221">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="26226-222">**스피어 피싱(첨부 파일)** 캠페인의 경우 메시지 본문에서 링크를 제거해야 합니다. 그렇지 않으면 메시지에 링크와 첨부 파일이 둘 다 포함되고 링크 클릭은 첨부 파일 캠페인에서 추적되지 않습니다. **and**</span><span class="sxs-lookup"><span data-stu-id="26226-222">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![전자 메일 본문 작성](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="26226-224">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-224">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="26226-225">확인 단계에서 **마침을** **클릭하여** 캠페인을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-225">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="26226-226">피싱 메시지는 대상이 지정된 받는 사람에게 배달됩니다.</span><span class="sxs-lookup"><span data-stu-id="26226-226">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="26226-227">암호 공격 캠페인</span><span class="sxs-lookup"><span data-stu-id="26226-227">Password attack campaigns</span></span>

<span data-ttu-id="26226-228">암호 *공격자는* 일반적으로 하나 이상의 유효한 사용자 계정을 식별한 후 조직에서 사용자 계정에 대한 암호를 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-228">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="26226-229">공격 시뮬레이터에서는 사용자 암호의 복잡성을 테스트하기 위해 두 가지 유형의 암호 공격 캠페인을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-229">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="26226-230">**무기대 암호 입력(사전 공격):** 무제한 암호 *대키 공격(Brute force or* *Dictionary* Attack)은 사용자 계정에서 암호의 대량 사전 파일을 사용하며, 이 중 하나가 작동할(계정 하나에 대해 다수의 암호).</span><span class="sxs-lookup"><span data-stu-id="26226-230">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="26226-231">잘못된 암호 잠금이 제공되는 경우 암호 입력기 공격을 더 이상 해소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-231">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="26226-232">사전 공격의 경우 시도할 암호를 하나 이상 지정(수동 입력 또는 업로드된 파일으로)하고 한 명 이상의 사용자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-232">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="26226-233">**암호 스프레이 공격:** *암호 스프레이* 공격은 사용자 계정 목록에 대해 신중하게 고려되는 암호를 사용합니다(계정 하나에 대해 암호 하나).</span><span class="sxs-lookup"><span data-stu-id="26226-233">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="26226-234">암호 스프레이 공격은 무제한 암호 대비 공격(공격자가 암호를 수천 또는 수백 개의 계정으로 시도할 때 사용자의 잘못된 암호 잠금을 시도할 위험 없이)을 시도할 때 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-234">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="26226-235">암호 스프레이 공격의 경우 한 번에 시도할 암호만 지정하면 되지만 사용자를 한 명 이상 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-235">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="26226-236">공격 시뮬레이터의 암호 공격은 사용자 이름 및 암호 기본 인증 요청을 끝점으로 전달하므로 다른 인증 방법(AD FS, 암호 해시 동기화, 통과, PingFederate 등)과 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-236">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="26226-237">MFA를 사용하도록 설정한 사용자의 경우 암호 공격이 실제 암호를 시도하더라도 항상 실패로 등록됩니다(즉, MFA 사용자는 캠페인 **성공 시도** 횟수에 표시되지 않음).</span><span class="sxs-lookup"><span data-stu-id="26226-237">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="26226-238">이것은 예상된 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-238">This is the expected result.</span></span> <span data-ttu-id="26226-239">MFA는 암호 공격으로부터 보호하는 데 도움이 되는 기본 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-239">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="26226-240">암호 공격 캠페인 만들기 및 시작</span><span class="sxs-lookup"><span data-stu-id="26226-240">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="26226-241">보안 그룹 의& 규정 준수 센터에서 **위협 관리** \> **공격 시뮬레이터로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="26226-241">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="26226-242">공격 **시뮬레이트** 페이지에서, 만들고자 하는 캠페인의 유형에 따라 다음 선택 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-242">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="26226-243">**Brute Force Password(사전 공격)** 섹션에서 공격 시작을 **클릭하거나 공격 세부** **정보** \> **실행을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="26226-243">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="26226-244">비고 **있는 비행기 공격 섹션에서 공격** 시작을 **클릭하거나 공격** 세부 정보 실행 **Attack Details** \> **공격을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="26226-244">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="26226-245">암호 **공격 구성 마법사가** 새 플라이아웃에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="26226-245">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="26226-246">시작 **단계에서** 캠페인의 고유한 표시 이름을 입력하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="26226-246">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="26226-247">대상 **사용자 단계에서** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-247">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="26226-248">주소록을 **클릭하여** 캠페인의 받는 사람(사용자 또는 그룹)을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-248">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="26226-249">대상이 지정된 각 받는 사람은 Exchange Online 사서함이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-249">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="26226-250">검색 조건을 **입력하지 않고 필터를** 적용하고 적용을 클릭하면 모든 받는 사람이 반환되며 캠페인에 추가됩니다. **Filter**</span><span class="sxs-lookup"><span data-stu-id="26226-250">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="26226-251">가져오기를 클릭한 **다음 가져오기를** 클릭하여 쉼표로 구분된 값(CSV) 또는 줄으로 구분된 전자 메일 주소 파일을 가져옵니다. **Import**</span><span class="sxs-lookup"><span data-stu-id="26226-251">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="26226-252">각 줄에는 받는 사람의 전자 메일 주소가 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-252">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="26226-253">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-253">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="26226-254">공격 설정 **선택 단계에서** 캠페인 유형을 기준으로 수행할 작업을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-254">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="26226-255">**무제한 암호 대안(사전 공격):** 다음 단계 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-255">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="26226-256">**암호 수동 입력:** Enter 키를 **눌러 암호 추가 단추에 암호를** 입력한 다음 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="26226-256">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="26226-257">필요한 만큼 이 단계를 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-257">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="26226-258">**사전 파일에서 암호 업로드:** 업로드를 **클릭하여** 각 줄에 하나의 암호와 마지막 줄에 하나의 암호가 포함된 기존 텍스트 파일을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="26226-258">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="26226-259">텍스트 파일의 크기는 10MB 이하여하여 암호가 30000개를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-259">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="26226-260">**암호 스프레이**공격: **공격란에 사용할 암호를 입력하면 암호를** 하나 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-260">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="26226-261">작업을 마친 후 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-261">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="26226-262">확인 단계에서 **마침을** **클릭하여** 캠페인을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-262">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="26226-263">지정한 사용자에게 암호가 시도됩니다.</span><span class="sxs-lookup"><span data-stu-id="26226-263">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="26226-264">캠페인 결과 보기</span><span class="sxs-lookup"><span data-stu-id="26226-264">View campaign results</span></span>

<span data-ttu-id="26226-265">캠페인을 시작한 후 기본 시뮬레이션 공격 페이지에서 **진행 상황 및 결과를 확인할 수** 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-265">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="26226-266">활성 캠페인에는 상태 표시줄, 완료된 백분율 값 및 "(완료된 사용자) 수"의 "(완료된 사용자)" 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="26226-266">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="26226-267">새로 고침 **단추를** 클릭하면 활성 캠페인의 진행률이 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="26226-267">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="26226-268">활성 **캠페인을 중지하려면** 종료를 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-268">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="26226-269">캠페인이 완료되면 상태가 공격 완료로 **변경됩니다.**</span><span class="sxs-lookup"><span data-stu-id="26226-269">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="26226-270">다음 작업 중 하나를 수행하여 캠페인의 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-270">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="26226-271">주요 **시뮬레이트 공격 페이지에서** **캠페인 이름** 아래에 있는 보고서 보기를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-271">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="26226-272">주요 **시뮬레이트 페이지에서 공격** 유형에 **대한 섹션에서** 공격 세부 정보를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-272">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="26226-273">공격 **정보 페이지가** 열리면 공격 기록 섹션에서 **캠페인을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-273">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="26226-274">위의 작업은 공격 세부 정보라는 페이지로 **이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="26226-274">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="26226-275">다음 섹션에서는 이 페이지에 나와 있는 각 캠페인 유형에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-275">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="26226-276">스피어 피싱(자격 증명 도서) 캠페인 결과</span><span class="sxs-lookup"><span data-stu-id="26226-276">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="26226-277">각 캠페인의 공격 **세부 정보 페이지에서** 다음 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-277">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="26226-278">캠페인의 기간(시작 날짜/시간 및 종료 날짜/시간)입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-278">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="26226-279">**총 대상 사용자 수**</span><span class="sxs-lookup"><span data-stu-id="26226-279">**Total users targeted**</span></span>

- <span data-ttu-id="26226-280">**시도 성공:** 링크를 클릭하고 자격 **증명(모든** 사용자 이름 및 암호*값)을 입력한 사용자* 수입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-280">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="26226-281">**전체 성공률: 성공한**총 사용자 수 계산의 총 **성공률입니다.**  /  **Total users targeted**</span><span class="sxs-lookup"><span data-stu-id="26226-281">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="26226-282">**클릭을 최후:** 캠페인을 시작한 후 첫 번째 사용자가 링크를 클릭하는 데 걸리는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-282">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="26226-283">**평균 클릭**: 모든 사람이 링크를 클릭한 사용자 수로 나누어진 기간의 계산입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-283">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="26226-284">**성공 률:**(링크를 클릭한 사용자 수) / 대상으로 지정된 총 사용자 수)에 **의해 계산되는 비율입니다.**</span><span class="sxs-lookup"><span data-stu-id="26226-284">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="26226-285">**최고 자격 증명:** 캠페인을 시작한 후 첫 번째 사용자가 자격 증명을 입력하도록 한 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-285">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="26226-286">**Average Credentials**: 누가 모든 사용자가 자격 증명을 입력하는 데 걸린 시간을 해당 자격 증명을 입력한 사용자의 수로 나누는 기간의 계산입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-286">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="26226-287">**자격 증명 성공률:**(자격 증명을 입력한 사용자 수) / 대상으로 지정된 총 사용자 수에 의해 **계산되는 비율입니다.**</span><span class="sxs-lookup"><span data-stu-id="26226-287">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="26226-288">클릭한 항목과 하간 자격 **증명 제공 수를** 보여 주는 막대 그래프입니다. **Credential supplied**</span><span class="sxs-lookup"><span data-stu-id="26226-288">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="26226-289">클릭한 **링크,** 제공 되는 자격 **증명**및 없음 퍼스크리스를 보여 주는 원 그래프. **None**</span><span class="sxs-lookup"><span data-stu-id="26226-289">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="26226-290">위의 **사용자 섹션에는 링크를** 클릭한 사용자의 세부 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="26226-290">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="26226-291">사용자의 전자 메일 주소</span><span class="sxs-lookup"><span data-stu-id="26226-291">The user's email address</span></span>

  - <span data-ttu-id="26226-292">링크를 클릭할 때의 날짜/시간입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-292">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="26226-293">클라이언트 IP 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-293">The client IP address.</span></span>

  - <span data-ttu-id="26226-294">사용자의 Windows 및 웹 브라우저 버전에 대한 세부 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-294">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="26226-295">내보내기를 **클릭하여 결과를** CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-295">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="26226-296">스피어 피싱(첨부 파일) 캠페인 결과</span><span class="sxs-lookup"><span data-stu-id="26226-296">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="26226-297">각 캠페인의 공격 **세부 정보 페이지에서** 다음 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-297">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="26226-298">캠페인의 기간(시작 날짜/시간 및 종료 날짜/시간)입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-298">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="26226-299">**총 대상 사용자 수**</span><span class="sxs-lookup"><span data-stu-id="26226-299">**Total users targeted**</span></span>

- <span data-ttu-id="26226-300">**시도 성공:** 첨부 파일을 열거나 다운로드한 사용자 수입니다(미리 보기는 계산되지 않음).</span><span class="sxs-lookup"><span data-stu-id="26226-300">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="26226-301">**전체 성공률: 성공한**총 사용자 수 계산의 총 **성공률입니다.**  /  **Total users targeted**</span><span class="sxs-lookup"><span data-stu-id="26226-301">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="26226-302">**응용 프로그램 열기 시간:** 첫 번째 사용자가 캠페인을 실행한 후 첨부 파일을 여는 데 걸린 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-302">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="26226-303">**평균 첨부 파일 열기 시간:** 각 사용자가 첨부 파일을 열어 포함한 사용자의 수로 나누는 데 걸린 시간의 총 시간을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="26226-303">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="26226-304">**첨부 파일 열기 성공 률:**(첨부 파일을 연 사용자 수) / 대상으로 지정된 총 사용자 수에 의해 **계산되는 백분율입니다.**</span><span class="sxs-lookup"><span data-stu-id="26226-304">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="26226-305">Brute Force Password (Dictionary Attack) 캠페인 결과</span><span class="sxs-lookup"><span data-stu-id="26226-305">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="26226-306">각 캠페인의 공격 **세부 정보 페이지에서** 다음 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-306">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="26226-307">캠페인의 기간(시작 날짜/시간 및 종료 날짜/시간)입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-307">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="26226-308">**총 대상 사용자 수**</span><span class="sxs-lookup"><span data-stu-id="26226-308">**Total users targeted**</span></span>

- <span data-ttu-id="26226-309">**성공적인 시도:** 지정된 암호 중 하나를 사용하여 찾은 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-309">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="26226-310">**전체 성공률: 성공한**총 사용자 수 계산의 총 **성공률입니다.**  /  **Total users targeted**</span><span class="sxs-lookup"><span data-stu-id="26226-310">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="26226-311">위의 **검토된 사용자 섹션에는 영향을** 받는 사용자의 전자 메일 주소가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="26226-311">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="26226-312">내보내기를 **클릭하여 결과를** CSV 파일로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-312">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="26226-313">암호 스프레인 공격 캠페인 결과</span><span class="sxs-lookup"><span data-stu-id="26226-313">Password spray attack campaign results</span></span>

<span data-ttu-id="26226-314">각 캠페인의 공격 **세부 정보 페이지에서** 다음 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="26226-314">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="26226-315">캠페인의 기간(시작 날짜/시간 및 종료 날짜/시간)입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-315">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="26226-316">**총 대상 사용자 수**</span><span class="sxs-lookup"><span data-stu-id="26226-316">**Total users targeted**</span></span>

- <span data-ttu-id="26226-317">**성공적인 시도:** 지정된 암호를 사용하여 찾은 사용자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="26226-317">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="26226-318">**전체 성공률: 성공한**총 사용자 수 계산의 총 **성공률입니다.**  /  **Total users targeted**</span><span class="sxs-lookup"><span data-stu-id="26226-318">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
