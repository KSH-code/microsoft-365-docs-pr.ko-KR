---
title: 웹 사이트에서 Webex Teams 커넥터 Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 관리자는 Veritas의 Webex Teams 커넥터에서 데이터를 가져오고 보관할 커넥터를 Microsoft 365. 이 커넥터를 사용하면 타사 데이터 원본의 데이터를 보관할 수 Microsoft 365 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용하여 조직의 타사 데이터를 관리할 수 있습니다.
ms.openlocfilehash: 654ca53fd4cd7c6091ff74360545ba335f753ffd
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163907"
---
# <a name="set-up-a-connector-to-archive-webex-teams-data"></a><span data-ttu-id="5ec29-104">Webex 데이터 보관 커넥터 Teams 설정</span><span class="sxs-lookup"><span data-stu-id="5ec29-104">Set up a connector to archive Webex Teams data</span></span>

<span data-ttu-id="5ec29-105">Microsoft 365 준수 센터의 Veritas 커넥터를 사용하여 Webex 2013에서 Teams 조직의 사용자 사서함으로 데이터를 Microsoft 365 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-105">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from Webex Teams to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="5ec29-106">Veritas는 [Webex](https://globanet.com/webex-teams/) Teams 통신 항목을 캡처하고 가져오도록 구성된 Webex Teams 커넥터를 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ec29-106">Veritas provides a [Webex Teams](https://globanet.com/webex-teams/) connector that is configured to capture Webex Teams communication items and import them to Microsoft 365.</span></span> <span data-ttu-id="5ec29-107">커넥터는 조직의 Webex Teams 계정에서 1:1 채팅, 그룹 대화, 채널 대화 및 첨부 파일과 같은 Webex Teams 콘텐츠를 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 조직의 사용자 사서함으로 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ec29-107">The connector converts content from Webex Teams, such as 1:1 chats, group conversations, channel conversations, and attachments from your organization's Webex Teams account, to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="5ec29-108">Webex Teams 사서함에 저장한 후 소송 보존, eDiscovery Microsoft 365 보존 정책 및 보존 레이블, 통신 준수와 같은 Microsoft 365 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-108">After Webex Teams data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="5ec29-109">Webex Teams 커넥터를 사용하여 조직의 데이터를 Microsoft 365 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-109">Using a Webex Teams connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-webex-teams-data"></a><span data-ttu-id="5ec29-110">Webex 데이터 보관 Teams 개요</span><span class="sxs-lookup"><span data-stu-id="5ec29-110">Overview of archiving Webex Teams data</span></span>

<span data-ttu-id="5ec29-111">다음 개요에서는 커넥터를 사용하여 웹ex 서버의 데이터를 보관하는 Teams Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5ec29-111">The following overview explains the process of using a connector to archive Webex Teams data in Microsoft 365.</span></span>

![Webex 데이터 보관 Teams 워크플로](../media/WebexTeamsConnectorWorkflow.png)

1. <span data-ttu-id="5ec29-113">조직은 Webex 사이트와 함께 Teams 웹ex 웹 사이트를 설정하고 Teams 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-113">Your organization works with Webex Teams to set up and configure a Webex Teams site.</span></span>

2. <span data-ttu-id="5ec29-114">24시간마다 Webex Teams Veritas Merge1 사이트에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-114">Once every 24 hours, Webex Teams items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="5ec29-115">또한 이 커넥터는 Webex Teams 전자 메일 메시지 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-115">The connector also converts the Webex Teams items to an email message format.</span></span>

3. <span data-ttu-id="5ec29-116">Microsoft 365 준수 센터에서 만든 Webex Teams 커넥터는 매일 Veritas Merge1에 연결하고 Webex Teams 항목을 Microsoft 클라우드의 보안 Azure Storage 위치로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-116">The Webex Teams connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 every day, and transfers the Webex Teams items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="5ec29-117">커넥터는 3단계에 설명된 자동 사용자 매핑의 *Email* 속성 값을 사용하여 특정 사용자의 사서함으로 항목을 [가져올 수 있습니다.](#step-3-map-users-and-complete-the-connector-setup)</span><span class="sxs-lookup"><span data-stu-id="5ec29-117">The connector imports items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="5ec29-118">Webex Teams 폴더의 하위 폴더가 사용자 **사서함에** 만들어지며 해당 폴더로 항목이 가져오기됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-118">A subfolder in the Inbox folder named **Webex Teams** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="5ec29-119">이 커넥터는 Email 속성 값을 사용하여 이 *기능을* 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="5ec29-120">모든 Webex Teams 항목에는 항목의 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-120">Every Webex Teams item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5ec29-121">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="5ec29-121">Before you begin</span></span>

- <span data-ttu-id="5ec29-122">Microsoft 커넥터에 대한 Veritas Merge1 계정을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-122">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="5ec29-123">이 계정을 만들하려면 [Veritas 고객 지원에 문의하세요.](https://globanet.com/ms-connectors-contact)</span><span class="sxs-lookup"><span data-stu-id="5ec29-123">To create this account, contact [Veritas Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="5ec29-124">1단계에서 커넥터를 만들 때 이 계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="5ec29-125">에서 응용 프로그램을 만들어 Webex 계정에서 데이터를 [https://developer.webex.com/](https://developer.webex.com) Teams.</span><span class="sxs-lookup"><span data-stu-id="5ec29-125">Create an application at [https://developer.webex.com/](https://developer.webex.com) to fetch data from your Webex Teams account.</span></span> <span data-ttu-id="5ec29-126">응용 프로그램을 만드는 방법에 대한 단계별 지침은 [Merge1 Third-Party Connectors User Guide를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="5ec29-126">For step-by step instructions about creating the application, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)</span></span>

   <span data-ttu-id="5ec29-127">이 응용 프로그램을 만들면 Webex 플랫폼에서 고유한 자격 증명 집합을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-127">When you create this application, the Webex platform generates a set of unique credentials.</span></span> <span data-ttu-id="5ec29-128">이러한 자격 증명은 Global Merge1 사이트에서 Webex Teams 커넥터를 구성할 때 2단계에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-128">These credentials are used in Step 2 when you configure the Webex Teams connector on the Global Merge1 site.</span></span>

- <span data-ttu-id="5ec29-129">1단계에서 Webex Teams 커넥터를 만들고 3단계에서 완료하는 사용자는 2단계에서 사서함 가져오기 내보내기 역할에 할당해야 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5ec29-129">The user who creates the Webex Teams connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="5ec29-130">이 역할은 준수 센터의  데이터 커넥터 페이지에서 커넥터를 Microsoft 365 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-130">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="5ec29-131">기본적으로 이 역할은 역할 그룹의 역할 그룹에 할당되지 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5ec29-131">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="5ec29-132">사서함 가져오기 내보내기 역할을 조직의 조직 관리 역할 그룹에 추가할 수 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5ec29-132">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="5ec29-133">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-133">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="5ec29-134">자세한 내용은 "역할 [](/Exchange/permissions-exo/role-groups#create-role-groups) 그룹에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5ec29-134">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-webex-teams-connector"></a><span data-ttu-id="5ec29-135">1단계: Webex Teams 설정</span><span class="sxs-lookup"><span data-stu-id="5ec29-135">Step 1: Set up the Webex Teams connector</span></span>

<span data-ttu-id="5ec29-136">첫 번째 단계는 데이터 커넥터에 액세스하고 [Webex](https://globanet.com/webex-teams/) 커넥터를 설정하는 Teams 것입니다. </span><span class="sxs-lookup"><span data-stu-id="5ec29-136">The first step is to gain access to the **Data Connectors** and set up the [Webex Teams](https://globanet.com/webex-teams/) connector.</span></span>

1. <span data-ttu-id="5ec29-137">으로 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 이동한 다음 **데이터** 커넥터  >  **Webex 를 Teams.**</span><span class="sxs-lookup"><span data-stu-id="5ec29-137">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Webex Teams**.</span></span>

2. <span data-ttu-id="5ec29-138">**Webex Teams** 설명 페이지에서 커넥터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ec29-138">On the **Webex Teams** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="5ec29-139">서비스 **약관 페이지에서** 동의를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ec29-139">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="5ec29-140">커넥터를 식별하는 고유한 이름을 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="5ec29-140">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="5ec29-141">Merge1 계정에 로그인하여 커넥터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-141">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-webex-teams-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="5ec29-142">2단계: Veritas Merge1 사이트에서 webex Teams 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="5ec29-142">Step 2: Configure the Webex Teams connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="5ec29-143">두 번째 단계는 Merge1 사이트에서 Webex Teams 커넥터를 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-143">The second step is to configure the Webex Teams connector on the Merge1 site.</span></span> <span data-ttu-id="5ec29-144">Webex Teams 구성하는 방법에 대한 자세한 내용은 [Merge1 Third-Party Connectors User Guide를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="5ec29-144">For information about how to configure the Webex Teams connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="5ec29-145">저장 및 & **마친** 후  준수 센터의 커넥터 마법사에 Microsoft 365 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-145">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="5ec29-146">3단계: 사용자 매핑 및 커넥터 설정 완료</span><span class="sxs-lookup"><span data-stu-id="5ec29-146">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="5ec29-147">사용자를 매핑하고 Microsoft 365 준수 센터에서 커넥터 설정을 완료하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-147">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="5ec29-148">**Webex 매핑 Teams 사용자 Microsoft 365** 자동 사용자 매핑을 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="5ec29-148">On the **Map Webex Teams users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="5ec29-149">Webex Teams 항목에는 조직의 사용자에 대한 전자 메일 주소가 포함된 *Email이라는* 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-149">The Webex Teams items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="5ec29-150">커넥터가 이 주소를 Microsoft 365 사용자 사서함으로 항목을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-150">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="5ec29-151">**다음을** 클릭하고 설정을 검토한 다음  데이터 커넥터 페이지로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-151">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-webex-teams-connector"></a><span data-ttu-id="5ec29-152">4단계: Webex Teams 모니터링</span><span class="sxs-lookup"><span data-stu-id="5ec29-152">Step 4: Monitor the Webex Teams connector</span></span>

<span data-ttu-id="5ec29-153">Webex 커넥터를 만든 Teams 준수 센터에서 커넥터 상태를 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-153">After you create the Webex Teams connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="5ec29-154">으로 [https://compliance.microsoft.com](https://compliance.microsoft.com) 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-154">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="5ec29-155">커넥터 **탭을** 클릭한 다음 **Webex** Teams 선택하여 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-155">Click the **Connectors** tab and then select the **Webex Teams** connector to display the flyout page.</span></span> <span data-ttu-id="5ec29-156">이 페이지에는 커넥터에 대한 속성과 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-156">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="5ec29-157">원본이 있는 커넥터 상태  **아래에서** 로그 다운로드 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-157">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="5ec29-158">이 로그에는 Microsoft 클라우드로 가져온 데이터에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-158">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="5ec29-159">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="5ec29-159">Known issues</span></span>

- <span data-ttu-id="5ec29-160">현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-160">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="5ec29-161">더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ec29-161">Support for larger items will be available at a later date.</span></span>