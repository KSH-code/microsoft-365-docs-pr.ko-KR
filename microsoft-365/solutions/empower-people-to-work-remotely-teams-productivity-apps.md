---
title: 4단계. 원격 작업자 생산성 앱 및 서비스 배포
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 06/03/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
- M365solutions
ms.custom: ''
description: 사용자가 Teams, Exchange, SharePoint 및 기타 Microsoft 365 서비스를 사용하여 생산성을 향상시킬 수 있도록 합니다.
ms.openlocfilehash: 1c621ae797f32cd5b98af4c1eb7a341d0f976938
ms.sourcegitcommit: 9195c83c725a7e6ed395ce0253304da54e2195f0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "44560450"
---
# <a name="step-4-deploy-remote-worker-productivity-apps-and-services"></a><span data-ttu-id="a1626-104">4단계.</span><span class="sxs-lookup"><span data-stu-id="a1626-104">Step 4.</span></span> <span data-ttu-id="a1626-105">원격 작업자 생산성 앱 및 서비스 배포</span><span class="sxs-lookup"><span data-stu-id="a1626-105">Deploy remote worker productivity apps and services</span></span>

<span data-ttu-id="a1626-106">생산성을 높이려면 사용자가 서로 통신하고 공동 작업을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-106">To be productive, people need to communicate and collaborate with one another.</span></span> <span data-ttu-id="a1626-107">사용자들은 만나고, 음성 및 텍스트로 채팅하 고, 새 콘텐츠를 만들고, 정보 및 파일을 공유 하고, 전자 메일을 교환하고, 일정 및 작업을 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-107">They need to meet, chat by voice and text, create new content and share information and files, exchange email, and manage calendars and tasks.</span></span> <span data-ttu-id="a1626-108">Microsoft 365는 다음과 같은 모든 주요 기능에 대한 클라우드 기반 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-108">Microsoft 365 provides cloud-based services for all of these key functions:</span></span>

- <span data-ttu-id="a1626-109">사용자들이 떨어져서 작업하는 동안 그들의 연결을 유지하기 위해서 조직, 부서, 그리고 소규모 팀과 개인에게 모임을 위한 공동 통신 허브, 채팅 그리고 파일 저장소를 제공하는 Microsoft Teams를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-109">To keep people connected while they work apart, use Microsoft Teams, which provides a common hub of communication for meetings, chats, and file storage for the organization, departments, and for small teams and individuals.</span></span> 
- <span data-ttu-id="a1626-110">전자 메일을 교환하고 일정, 연락처 및 작업을 관리하는 데 Exchange Online과 Outlook 클라이언트를 사용하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-110">For exchanging email and managing calendars, contacts, and tasks, use Exchange Online and the Outlook client.</span></span>
- <span data-ttu-id="a1626-111">파일을 저장하고 공동 작업을 하려면 SharePoint 및 OneDrive를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-111">For storing and collaborating on files, use SharePoint and OneDrive.</span></span> <span data-ttu-id="a1626-112">이들은 웹 브라우저나 Teams 내에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-112">You can use them with a web browser or within Teams.</span></span>
- <span data-ttu-id="a1626-113">새 콘텐츠를 만들거나 기존 콘텐츠에 대해 공동 작업을 하는 데, Microsoft 365 앱은 로컬 컴퓨터에 설치된 Word, PowerPoint, Excel 및 Outlook 버전이며 지속적인 기능과 보안 업데이트를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-113">For creating new content or collaborating on existing content, Microsoft 365 Apps are versions of Word, PowerPoint, Excel, and Outlook that are installed on your local computer and receive ongoing feature and security updates.</span></span>

![Teams, Outlook, SharePoint, OneDrive 및 Microsoft 365 앱을 사용해서 생산성 유지](../media/empower-people-to-work-remotely/remote-workers-productivity-grid.png)

## <a name="keep-people-connected-with-microsoft-teams"></a><span data-ttu-id="a1626-115">Microsoft Teams를 통해 사용자들이 연결된 상태를 유지</span><span class="sxs-lookup"><span data-stu-id="a1626-115">Keep people connected with Microsoft Teams</span></span>

<span data-ttu-id="a1626-116">Teams를 사용하면 한 곳에서 채팅, 모임, 통화, 공동 작업을 모두 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-116">Teams allows you to chat, meet, call, and collaborate all in one place.</span></span> <span data-ttu-id="a1626-117">Teams는 팀워크를 위한 허브로 원격 작업을 하는 데 필요한 모든 것을 통합하고 있기에 수백만 명의 사용자가 매일 Teams에서 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-117">Millions of people get their work done in Teams every day because it brings together everything you need to work remotely into a hub for teamwork.</span></span> 

<span data-ttu-id="a1626-118">[이 문서](https://docs.microsoft.com/microsoftteams/support-remote-work-with-teams)를 Teams를 이용한 원격 작업자 지원 지침으로 사용할 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="a1626-118">Use [this article](https://docs.microsoft.com/microsoftteams/support-remote-work-with-teams) for guidance on supporting your remote workers with Teams.</span></span> 

<span data-ttu-id="a1626-119">원격 작업을 위한 Teams의 사용에 대한 지침 및 데모를 보려면 [동영상 파트 1](https://resources.techcommunity.microsoft.com/enabling-remote-work/#productivity)을 시청하세요.</span><span class="sxs-lookup"><span data-stu-id="a1626-119">Watch the [Part 1 video](https://resources.techcommunity.microsoft.com/enabling-remote-work/#productivity) for guidance and demos on using Teams for remote work.</span></span>

### <a name="chat-and-conversations"></a><span data-ttu-id="a1626-120">채팅 및 대화</span><span class="sxs-lookup"><span data-stu-id="a1626-120">Chat and conversations</span></span>

<span data-ttu-id="a1626-121">채팅 및 스레드된 대화는 개별 1:1 채팅 및 그룹 채팅 그리고 대화에 대한 지원과 함께 Teams의 중심에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-121">Chat and threaded conversations are at the center of Teams with support for individual 1:1 chats and group chats and conversations.</span></span> <span data-ttu-id="a1626-122">원격 직원은 그룹 채팅 혹은 1:1 메시지를 통해 정보, 의견, 그리고 개성을 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-122">Remote workers can share information, opinions, and personality by using gifs, stickers, and emojis in group chats or one-to-one messages.</span></span>

### <a name="meetings-and-conferencing"></a><span data-ttu-id="a1626-123">모임 및 회의</span><span class="sxs-lookup"><span data-stu-id="a1626-123">Meetings and conferencing</span></span> 

<span data-ttu-id="a1626-124">Teams는 확실히 원격 작업자들이(특히 최대 250명을 지원하는 모임) 연락을 유지하고 정보를 공유하는 데 도움이 됩니다. </span><span class="sxs-lookup"><span data-stu-id="a1626-124">Teams can certainly help maintain communications and information sharing with remote workers, especially with meetings that support up to 250 people.</span></span> <span data-ttu-id="a1626-125">Teams는 모임은 통해 조직의 내부 및 외부 사용자들과의 대화형 공동 작업 모임을 가능하게 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-125">Teams meetings enable interactive, collaborative meetings with people inside and outside your organization.</span></span> <span data-ttu-id="a1626-126">원격 작업자는 되풀이되는 프로젝트 검사점, 동료들과의 연락 유지, 브레인스토밍 세션, 고객과의 대화 촉진을 비롯한 일상적인 활동에 Teams 모임을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-126">Remote workers can use Teams meetings for day-to-day activities including recurring project checkpoints, catching-up with colleagues, brainstorming sessions, and facilitating conversations with customers.</span></span> 

### <a name="calling"></a><span data-ttu-id="a1626-127">통화</span><span class="sxs-lookup"><span data-stu-id="a1626-127">Calling</span></span>

<span data-ttu-id="a1626-128">Teams는 페더레이션을 사용하는 사용자들 및 심지어 다른 조직들 간에 직접 VoIP 통화를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-128">Teams supports direct VoIP calling between users and even other organizations using federation.</span></span> <span data-ttu-id="a1626-129">이는 모임과 동일한 코덱을 사용하고 추가 PSTN 요금없이 세계적으로 탁월한 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-129">It uses the same codecs as meetings and provide great audio world-wide without additional PSTN charges.</span></span> <span data-ttu-id="a1626-130">그러나 일부 사용는 원격으로 작업할 때 외부 전화를 받으려면 전용 전화 번호가 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-130">However, some users may need a dedicated phone number to take external calls when working remotely.</span></span> <span data-ttu-id="a1626-131">Teams는 이러한 사용자들이 전화를 걸고 받을 수 있도록 클라우드 전화 서비스를 신속하게 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-131">Teams can quickly provide cloud phone service for these users to make and receive phone calls.</span></span>

### <a name="apps-and-workflows"></a><span data-ttu-id="a1626-132">앱 및 워크플로</span><span class="sxs-lookup"><span data-stu-id="a1626-132">Apps and workflows</span></span>

<span data-ttu-id="a1626-133">Teams는 데스크톱, 웹 및 모바일 버전의 Teams에서 액세스할 수 있는 앱 및 워크플로를 위한 플랫폼을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-133">Teams provides a platform for apps and workflows that can be accessed from the desktop, web, and mobile versions of Teams.</span></span> <span data-ttu-id="a1626-134">Teams는 사용자를 참여시키고 생산성을 지원하며 일반적으로 사용되는 비즈니스 서비스를 Teams로 통합하기 위해 Microsoft 및 타사에서 게시한 수백 개의 앱을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-134">Teams provides hundreds of apps published by Microsoft and by third parties to engage users, support productivity, and integrate commonly used business services into Teams.</span></span> <span data-ttu-id="a1626-135">사용자 및 관리자 또한 낮은 코드의 전원 앱과 전원 자동화 개발 도구를 사용하여 Teams용 사용자 지정 앱 및 자동화된 워크플로를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-135">Users and Admins can also create custom apps and automated workflows for Teams using the low-code Power Apps and Power Automate development tools.</span></span>

<span data-ttu-id="a1626-136">앱과 워크플로는 작업자들이 중요한 정보를 수집 및 공유하고, 반복적인 작업을 자동화하며 대화형 봇과 채팅을 할 수 있도록 하여 Teams에서 그들의 생산성을 더욱 향상시킬 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-136">Apps and workflows let remote workers be more productive in Teams, by collecting and sharing critical information, automating repetitive tasks, and allowing them to chat with interactive bot.</span></span> <span data-ttu-id="a1626-137">앱을 채널이나 Teams 앱 바에 고정하는 것은 사용자가 이 앱을 관련 공간에서 쉽게 액세스할 수 있도록 하는 좋은 방법이며 관리자는 앱을 고정하여 모든 사용자가 사용해야 할 앱의 인식성 및 채택성을 견인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-137">Pinning apps to a channel or the Teams app bar is a great way for users to make these apps easily accessible in a relevant space, and admins can pin apps to drive awareness and adoption of the apps that everyone should be using.</span></span>

## <a name="exchange-email-and-manage-calendars-contacts-and-tasks-with-exchange-online-and-outlook"></a><span data-ttu-id="a1626-138">Exchange Online 및 Outlook을 이용하여 전자 메일을 교환하고 일정, 연락처, 작업을 관리</span><span class="sxs-lookup"><span data-stu-id="a1626-138">Exchange email and manage calendars, contacts, and tasks with Exchange Online and Outlook</span></span>

<span data-ttu-id="a1626-139">Outlook을 사용하면 원격 작업자는 연결 상태를 유지하고 전자 메일, 일정, 연락처, 작업 등을 모두 함께 계속해서 한 곳에서 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-139">With Outlook, remote workers can stay connected and organized with email, calendars, contacts, tasks, and more—together in one place.</span></span> <span data-ttu-id="a1626-140">Outlook을 사용하면 관련 항목에 따라 하루를 순조롭게 진행하고 우선순위를 지정하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-140">Outlook helps you stay on track and prioritize your day based on what’s relevant to you.</span></span> <span data-ttu-id="a1626-141">Outlook은 OneDrive에서 바로 첨부 파일을 공유하고, 팀 모임을 계획하고 모임에 참여하며, 일정을 보고 공유하고 다른 사용자에게 대리인 권한을 제공할 수 있도록 해줍니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-141">Outlook enables you to share attachments right from OneDrive, plan and join Teams meetings, view and share calendars, and provide delegate permissions to others.</span></span> <span data-ttu-id="a1626-142">직장 및 개인적 용무 모두의 측면에서 다음에 처리할 용무와 주의를 필요로 하는 사항을 아는 것은 원격 작업자들이 중요한 사항에 집중할 수 있도록 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-142">Knowing what’s coming up next across both work and personal commitments and what needs attention can help remote workers focus on what matters.</span></span> <span data-ttu-id="a1626-143">Outlook은 원격 작업자들이 그들의 시간 및 필요로 하는 사항을(예를 들어, 파일, 조직 내 사용자 등) 쉽게 관리하는 데 유용한 방법들을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-143">Outlook provides helpful ways for remote workers to manage their time and to find what they need easily, including files, people in the organization, and more.</span></span> 

<span data-ttu-id="a1626-144">최신 인증 및 조건부 액세스를 지원하는 조직의 전자 메일 및 메일 클라이언트를 보호하는 권장 ID와 정책은 [이 문서](../enterprise/secure-email-recommended-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1626-144">See [this article](../enterprise/secure-email-recommended-policies.md) for the recommended identity and device access policies to protect organizational email and email clients that support modern authentication and Conditional Access.</span></span>

## <a name="store-and-collaborate-on-files-with-sharepoint-online-and-onedrive"></a><span data-ttu-id="a1626-145">SharePoint Online 및 OneDrive를 사용한 파일 저장 및 공동 작업</span><span class="sxs-lookup"><span data-stu-id="a1626-145">Store and collaborate on files with SharePoint Online and OneDrive</span></span>

<span data-ttu-id="a1626-146">콘텐츠 공동 작업의 경우 원격 작업자는 SharePoint Online 및 OneDrive 폴더를 클라우드의 중앙 위치로 사용하여 파일을 저장하고, 공동 작성하고, 통신하고 공동 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-146">For content collaboration, remote workers can use SharePoint Online and OneDrive folders as a central place in the cloud to store and share files, co-author, communicate, and collaborate.</span></span> <span data-ttu-id="a1626-147">원격 작업자는 웹 브라우저, Teams 그리고 Office 앱을 통해 어디에서나 안전하게 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-147">Remote workers can securely work from anywhere from a web browser, from Teams, and from Office apps.</span></span>

<span data-ttu-id="a1626-148">SharePoint Online 및 비즈니스용 OneDrive를 보호하기 위한 권장 ID 및 장치 액세스 정책은 [이 문서](../enterprise/sharepoint-file-access-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1626-148">See [this article](../enterprise/sharepoint-file-access-policies.md) for the recommended identity and device-access policies to protect SharePoint Online and OneDrive for Business.</span></span>

## <a name="create-and-collaborate-on-content-with-microsoft-365-apps"></a><span data-ttu-id="a1626-149">Microsoft 365 앱을 사용한 콘텐츠 만들기 및 공동 작업</span><span class="sxs-lookup"><span data-stu-id="a1626-149">Create and collaborate on content with Microsoft 365 Apps</span></span>

<span data-ttu-id="a1626-150">Microsoft 365 앱은 언제 어디에서나 사용자들이 원활하게 함께 작업할 수 있도록 해주는 기업에 가장 생산적이고 안전한 Office 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-150">Microsoft 365 Apps is the most productive and most secure Office experience for enterprises, allowing people to work together seamlessly from anywhere, anytime.</span></span> <span data-ttu-id="a1626-151">원격 작업자는 동시에 여러 사용자와 한 문서에 대해 공동 작업을 하고, 실시간으로 편집 및 변경된 내용을 보고, 모든 노트북, PC 또는 모바일 장치를 통해 다른 사용자들과 공동 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-151">Remote workers can collaborate on a document with multiple people simultaneously, see edits and changes in real time, and coauthor with others on any laptop, PC, or mobile device.</span></span>

<span data-ttu-id="a1626-152">엔터프라이즈 환경에서 Microsoft 365 앱을 계획, 배포 및 관리하려면 [이 문서](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a1626-152">See [this article](https://docs.microsoft.com/deployoffice/deployment-guide-microsoft-365-apps) to plan, deploy, and manage Microsoft 365 Apps in your enterprise environment.</span></span>

## <a name="admin-technical-resources-for-productivity-apps-and-services"></a><span data-ttu-id="a1626-153">생산성 앱 및 서비스를 위한 관리자 기술 리소스</span><span class="sxs-lookup"><span data-stu-id="a1626-153">Admin technical resources for productivity apps and services</span></span>

- [<span data-ttu-id="a1626-154">Microsoft Teams를 사용하여 원격 작업자 지원하기</span><span class="sxs-lookup"><span data-stu-id="a1626-154">Support remote workers using Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/support-remote-work-with-teams)
- [<span data-ttu-id="a1626-155">원격 작업자를 위한 Teams에 대한 동영상 파트 1</span><span class="sxs-lookup"><span data-stu-id="a1626-155">Part 1 video on Teams for remote workers</span></span>](https://resources.techcommunity.microsoft.com/enabling-remote-work/#productivity)
- [<span data-ttu-id="a1626-156">Teams 고객 성공 키트 다운로드</span><span class="sxs-lookup"><span data-stu-id="a1626-156">Teams Customer Success Kit download</span></span>](https://www.microsoft.com/download/details.aspx?id=54244)
- [<span data-ttu-id="a1626-157">Teams의 채택을 촉진하기 위한 도구</span><span class="sxs-lookup"><span data-stu-id="a1626-157">Tools for driving Teams adoption</span></span>](https://docs.microsoft.com/microsoftteams/adopt-tools-and-downloads) 
- [<span data-ttu-id="a1626-158">Microsoft Teams에 대한 변경 관리 전략 만들기</span><span class="sxs-lookup"><span data-stu-id="a1626-158">Create a change management strategy for Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)
- [<span data-ttu-id="a1626-159">세 가지 보호 계층이 있는 Teams</span><span class="sxs-lookup"><span data-stu-id="a1626-159">Teams with three tiers of protection</span></span>](configure-teams-three-tiers-protection.md)

## <a name="user-training-resources-for-productivity-apps-and-services"></a><span data-ttu-id="a1626-160">생산성 앱과 서비스에 대한 사용자 교육 리소스</span><span class="sxs-lookup"><span data-stu-id="a1626-160">User training resources for productivity apps and services</span></span>

- [<span data-ttu-id="a1626-161">Office 및 Office 365에 대한 사용자 교육</span><span class="sxs-lookup"><span data-stu-id="a1626-161">Train your users on Office and Office 365</span></span>](https://support.office.com/article/train-your-users-on-office-and-microsoft-365-7cba3c97-7f19-46ed-a1c6-763971a26c2)
- [<span data-ttu-id="a1626-162">웹용 Office 사용</span><span class="sxs-lookup"><span data-stu-id="a1626-162">Use Office for the web</span></span>](https://support.microsoft.com/office/get-started-with-office-for-the-web-in-microsoft-365-5622c7c9-721d-4b3d-8cb9-a7276c2470e5)

## <a name="next-step"></a><span data-ttu-id="a1626-163">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a1626-163">Next step</span></span>

<span data-ttu-id="a1626-164">[5단계](empower-people-to-work-remotely-communication-venues.md)를 계속 진행하여 원격 작업자에게 서비스를 제공하는 추가 통신 장소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a1626-164">Continue with [Step 5](empower-people-to-work-remotely-communication-venues.md) to create additional communication venues that serve your remote workers.</span></span>
