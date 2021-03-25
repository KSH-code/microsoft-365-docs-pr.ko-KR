---
title: Microsoft 365에서 Reuters Eikon 데이터를 보관하는 커넥터 설정
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
description: 관리자는 Microsoft 365의 Veritas에서 Reuters Eikon 데이터를 가져오고 보관하는 커넥터를 설정할 수 있습니다. 이 커넥터를 사용하면 타사 데이터 원본의 데이터를 Microsoft 365에 보관할 수 있습니다. 이 데이터를 보관한 후 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용하여 타사 데이터를 관리할 수 있습니다.
ms.openlocfilehash: f3e0c9d542f54a46703b4acd0c1f154d3ab84cb8
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164103"
---
# <a name="set-up-a-connector-to-archive-reuters-eikon-data"></a><span data-ttu-id="a2eb3-105">Reuters Eikon 데이터를 보관할 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="a2eb3-105">Set up a connector to archive Reuters Eikon data</span></span>

<span data-ttu-id="a2eb3-106">Microsoft 365 규정 준수 센터의 Veritas 커넥터를 사용하여 Reuters Eikon 플랫폼에서 Microsoft 365 조직의 사용자 사서함으로 데이터를 가져오고 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Reuters Eikon platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="a2eb3-107">Veritas는 타사 데이터 원본의 항목을 정기적으로 캡처하고 해당 항목을 Microsoft 365로 가져오도록 구성된 [Reuters Eikon](https://globanet.com/eikon/) 커넥터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-107">Veritas provides a [Reuters Eikon](https://globanet.com/eikon/) connector that is configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="a2eb3-108">커넥터는 사용자 Reuters Eikon 계정의 일대일 메시지, 그룹 채팅, 첨부 파일 및 고지와 같은 콘텐츠를 전자 메일 메시지 형식으로 변환한 다음 Microsoft 365의 사용자 사서함으로 해당 항목을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-108">The connector converts the content such as person-to-person messages, group chats, attachments, and disclaimers from a user's Reuters Eikon account to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="a2eb3-109">Reuters Eikon 데이터가 사용자 사서함에 저장되고 나면 소송 보존, eDiscovery, 보존 정책 및 보존 레이블, 통신 준수와 같은 Microsoft 365 규정 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-109">After Reuters Eikon data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="a2eb3-110">Reuters Eikon 커넥터를 사용하여 Microsoft 365에서 데이터를 가져오고 보관하면 조직이 정부 및 규제 정책을 준수하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-110">Using a Reuters Eikon connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-reuters-eikon-data"></a><span data-ttu-id="a2eb3-111">보관 로이터 Eikon 데이터 개요</span><span class="sxs-lookup"><span data-stu-id="a2eb3-111">Overview of archiving Reuters Eikon data</span></span>

<span data-ttu-id="a2eb3-112">다음 개요에서는 커넥터를 사용하여 Microsoft 365에서 Reuters Eikon 데이터를 보관하는 프로세스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-112">The following overview explains the process of using a connector to archive Reuters Eikon data in Microsoft 365.</span></span>

![Reuters Eikon 데이터에 대한 보관 워크플로](../media/ReutersEikonConnectorWorkflow.png)

1. <span data-ttu-id="a2eb3-114">조직은 Reuters Eikon과 함께 Reuters Eikon 사이트를 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-114">Your organization works with Reuters Eikon to set up and configure a Reuters Eikon site.</span></span>

2. <span data-ttu-id="a2eb3-115">24시간마다 Reuters Eikon 항목이 Veritas Merge1 사이트에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-115">Once every 24 hours, Reuters Eikon items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="a2eb3-116">또한 커넥터는 Reuters Eikon 항목을 전자 메일 메시지 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-116">The connector also converts Reuters Eikon items to an email message format.</span></span>

3. <span data-ttu-id="a2eb3-117">Microsoft 365 규정 준수 센터에서 만드는 Reuters Eikon 커넥터는 매일 Veritas Merge1 사이트에 연결하고 콘텐츠를 Microsoft 클라우드의 보안 Azure Storage 위치로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-117">The Reuters Eikon connector that you create in the Microsoft 365 compliance center connects to the Veritas Merge1 site every day and transfers the content to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="a2eb3-118">커넥터는 3단계에 설명된 자동 사용자 매핑의 *Email* 속성 값을 사용하여 특정 사용자의 사서함으로 항목을 [가져올 수 있습니다.](#step-3-map-users-and-complete-the-connector-setup)</span><span class="sxs-lookup"><span data-stu-id="a2eb3-118">The connector imports items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="a2eb3-119">**Reuters Eikon이라는** 받은 편지함 폴더의 하위 폴더가 사용자 사서함에 만들어지며 항목이 해당 폴더로 가져오기됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-119">A subfolder in the Inbox folder named **Reuters Eikon** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="a2eb3-120">커넥터는 Email 속성 값을 사용하여 항목을 가져올 사서함을 결정할 *수* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="a2eb3-121">모든 Reuters Eikon 항목에는 항목의 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-121">Every Reuters Eikon item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a2eb3-122">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="a2eb3-122">Before you begin</span></span>

- <span data-ttu-id="a2eb3-123">Microsoft 커넥터에 대한 Veritas Merge1 계정을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-123">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="a2eb3-124">계정을 만들하려면 [Veritas 고객 지원에 문의하세요.](https://globanet.com/ms-connectors-contact)</span><span class="sxs-lookup"><span data-stu-id="a2eb3-124">To create an account, contact [Veritas Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="a2eb3-125">1단계에서 커넥터를 만들 때 이 계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="a2eb3-126">1단계에서 Reuters Eikon 커넥터를 만들고 3단계에서 완료하는 사용자는 Exchange Online의 사서함 가져오기 내보내기 역할에 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-126">The user who creates the Reuters Eikon connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="a2eb3-127">이 역할은 Microsoft 365 규정 준수 센터의 데이터 커넥터 페이지에서 커넥터를 추가하는 데 필요합니다. </span><span class="sxs-lookup"><span data-stu-id="a2eb3-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="a2eb3-128">기본적으로 이 역할은 Exchange Online의 역할 그룹에 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-128">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="a2eb3-129">Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="a2eb3-130">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="a2eb3-131">자세한 내용은 "Exchange [](/Exchange/permissions-exo/role-groups#create-role-groups) Online에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-131">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-reuters-eikon-connector"></a><span data-ttu-id="a2eb3-132">1단계: Reuters Eikon 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="a2eb3-132">Step 1: Set up the Reuters Eikon connector</span></span>

<span data-ttu-id="a2eb3-133">첫 번째 단계는 Microsoft  365 규정 준수 센터의 데이터 커넥터 페이지에 액세스하고 Reuters Eikon 데이터에 대한 커넥터를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for Reuters Eikon data.</span></span>

1. <span data-ttu-id="a2eb3-134">으로 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 이동한 다음 **데이터** 커넥터  >  **Reuters Eikon을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2eb3-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Reuters Eikon**.</span></span>

2. <span data-ttu-id="a2eb3-135">**Reuters Eikon** 제품 설명 페이지에서 커넥터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2eb3-135">On the **Reuters Eikon** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="a2eb3-136">서비스 **약관 페이지에서** 동의를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2eb3-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="a2eb3-137">커넥터를 식별하는 고유한 이름을 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="a2eb3-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="a2eb3-138">Merge1 계정에 로그인하여 커넥터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-reuters-eikon-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="a2eb3-139">2단계: Veritas Merge1 사이트에서 Reuters Eikon 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="a2eb3-139">Step 2: Configure the Reuters Eikon connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="a2eb3-140">두 번째 단계는 Merge1 사이트에서 Reuters Eikon 커넥터를 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-140">The second step is to configure the Reuters Eikon connector on the Merge1 site.</span></span> <span data-ttu-id="a2eb3-141">Veritas Merge1 사이트에서 Reuters Eikon 커넥터를 구성하는 방법에 대한 자세한 내용은 [Merge1 Third-Party Connectors User Guide를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Eikon%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="a2eb3-141">For information about how to configure the Reuters Eikon connector on the Veritas Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Eikon%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="a2eb3-142">저장 및 & **마친** 후  Microsoft 365 규정 준수 센터의 커넥터 마법사에 있는 사용자 매핑 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="a2eb3-143">3단계: 사용자 매핑 및 커넥터 설정 완료</span><span class="sxs-lookup"><span data-stu-id="a2eb3-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="a2eb3-144">사용자를 매핑하고 Microsoft 365 규정 준수 센터에서 커넥터 설정을 완료하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="a2eb3-145">외부 사용자를 **Microsoft 365** 사용자에 매핑 페이지에서 자동 사용자 매핑을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-145">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="a2eb3-146">Reuters Eikon 항목에는 조직의 사용자에 대한 전자 메일 주소가 포함된 *Email이라는* 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-146">The Reuters Eikon items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="a2eb3-147">커넥터가 이 주소를 Microsoft 365 사용자와 연결하면 항목이 해당 사용자의 사서함으로 가져오기됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="a2eb3-148">**다음을** 클릭하고 설정을 검토한 다음  데이터 커넥터 페이지로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-148">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-reuters-eikon-connector"></a><span data-ttu-id="a2eb3-149">4단계: Reuters Eikon 커넥터 모니터링</span><span class="sxs-lookup"><span data-stu-id="a2eb3-149">Step 4: Monitor the Reuters Eikon connector</span></span>

<span data-ttu-id="a2eb3-150">Reuters Eikon 커넥터를 만든 후 Microsoft 365 규정 준수 센터에서 커넥터 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-150">After you create the Reuters Eikon connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="a2eb3-151">으로 [https://compliance.microsoft.com](https://compliance.microsoft.com) 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="a2eb3-152">커넥터 **탭을** 클릭한 다음 **Reuters Eikon** 커넥터를 선택하여 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-152">Click the **Connectors** tab and then select the **Reuters Eikon** connector to display the flyout page.</span></span> <span data-ttu-id="a2eb3-153">이 페이지에는 커넥터에 대한 속성과 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-153">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="a2eb3-154">원본이 있는 커넥터 상태  **아래에서** 로그 다운로드 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-154">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="a2eb3-155">이 로그에는 Microsoft 클라우드로 가져온 데이터에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-155">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="a2eb3-156">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="a2eb3-156">Known issues</span></span>

- <span data-ttu-id="a2eb3-157">현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-157">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="a2eb3-158">더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2eb3-158">Support for larger items will be available at a later date.</span></span>