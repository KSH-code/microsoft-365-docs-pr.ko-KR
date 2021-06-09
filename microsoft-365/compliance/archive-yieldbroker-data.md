---
title: 커넥터를 설정하여 검색에서 Yieldbroker 데이터를 Microsoft 365
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
description: 관리자는 Veritas에서 다른 사용자로 Yieldbroker 데이터를 가져오고 보관할 커넥터를 Microsoft 365. 이 커넥터를 사용하면 타사 데이터 원본의 데이터를 해당 커넥터에 Microsoft 365. 이 데이터를 보관한 후 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용하여 타사 데이터를 관리할 수 있습니다.
ms.openlocfilehash: 1f2ca6850057112cc0a97b08811532961a213e89
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163787"
---
# <a name="set-up-a-connector-to-archive-yieldbroker-data"></a><span data-ttu-id="9bd81-105">Yieldbroker 데이터를 보관할 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="9bd81-105">Set up a connector to archive Yieldbroker data</span></span>

<span data-ttu-id="9bd81-106">Microsoft 365 규정 준수 센터의 Veritas 커넥터를 사용하여 Yieldbroker에서 조직의 사용자 사서함으로 데이터를 Microsoft 365 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-106">Use a Veritas connector in the Microsoft 365 compliance center to import and archive data from the Yieldbroker to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="9bd81-107">Veritas는 타사 데이터 원본에서 항목을 캡처하고 해당 항목을 가져오도록 구성된 [Yieldbroker](https://globanet.com/yieldbroker/) 커넥터를 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9bd81-107">Veritas provides you with a [Yieldbroker](https://globanet.com/yieldbroker/) connector that's configured to capture items from the third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="9bd81-108">커넥터는 Yieldbroker의 콘텐츠를 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 사서함의 사용자 사서함으로 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9bd81-108">The connector converts the content from Yieldbroker to an email message format and then imports those items to the user’s mailbox in Microsoft 365.</span></span>

<span data-ttu-id="9bd81-109">Yieldbroker가 사용자 사서함에 저장되고 나면 소송 보존, Microsoft 365, 보존 정책 및 보존 레이블과 같은 Microsoft 365 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-109">After Yieldbroker is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies, and retention labels.</span></span> <span data-ttu-id="9bd81-110">Yieldbroker 커넥터를 사용하여 조직에서 데이터를 가져오고 Microsoft 365 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-110">Using a Yieldbroker connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-yieldbroker-data"></a><span data-ttu-id="9bd81-111">보관 Yieldbroker 데이터 개요</span><span class="sxs-lookup"><span data-stu-id="9bd81-111">Overview of archiving Yieldbroker data</span></span>

<span data-ttu-id="9bd81-112">다음 개요에서는 커넥터를 사용하여 각 커넥터의 Yieldbroker 데이터를 보관하는 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="9bd81-112">The following overview explains the process of using a connector to archive the Yieldbroker data in Microsoft 365.</span></span>

![Yieldbroker 데이터에 대한 보관 워크플로](../media/YieldbrokerConnectorWorkflow.png)

1. <span data-ttu-id="9bd81-114">조직은 Yieldbroker와 함께 작동하여 Yieldbroker 사이트를 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-114">Your organization works with the Yieldbroker to set up and configure a Yieldbroker site.</span></span>

2. <span data-ttu-id="9bd81-115">24시간마다 Yieldbroker 항목이 Veritas Merge1 사이트에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-115">Once every 24 hours, Yieldbroker items are copied to the Veritas Merge1 site.</span></span> <span data-ttu-id="9bd81-116">또한 커넥터는 콘텐츠를 전자 메일 메시지 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-116">The connector also converts the content to an email message format.</span></span>

3. <span data-ttu-id="9bd81-117">Microsoft 365 준수 센터에서 만든 Yieldbroker 커넥터는 매일 Veritas Merge1 사이트에 연결하여 Microsoft 클라우드의 보안 Azure Storage 위치로 메시지를 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-117">The Yieldbroker connector that you create in the Microsoft 365 compliance center, connects to the Veritas Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="9bd81-118">커넥터는 3단계에 설명된 자동 사용자 매핑의 *Email* 속성 값을 사용하여 변환된 Yieldbroker 항목을 특정 사용자의 사서함으로 [가져올 수 있습니다.](#step-3-map-users-and-complete-the-connector-setup)</span><span class="sxs-lookup"><span data-stu-id="9bd81-118">The connector imports the converted Yieldbroker items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="9bd81-119">받은 편지함 **폴더의 Yieldbroker** 하위 폴더가 사용자 사서함에 만들어지며 해당 폴더로 항목이 가져오기됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-119">A subfolder in the Inbox folder named **Yieldbroker** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="9bd81-120">커넥터는 Email 속성 값을 사용하여 항목을 가져올 사서함을 결정할 *수* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="9bd81-121">모든 Yieldbroker에는 항목의 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-121">Every Yieldbroker contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9bd81-122">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="9bd81-122">Before you begin</span></span>

- <span data-ttu-id="9bd81-123">Microsoft 커넥터에 대한 Veritas Merge1 계정을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-123">Create a Veritas Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="9bd81-124">계정을 만들하려면 [Veritas 고객 지원에 문의하세요.](https://www.veritas.com/content/support/)</span><span class="sxs-lookup"><span data-stu-id="9bd81-124">To create an account, contact [Veritas Customer Support](https://www.veritas.com/content/support/).</span></span> <span data-ttu-id="9bd81-125">1단계에서 커넥터를 만들 때 이 계정에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="9bd81-126">1단계에서 Yieldbroker 커넥터를 만들고 3단계에서 완료하는 사용자는 2단계에서 사서함 가져오기 내보내기 역할에 할당해야 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9bd81-126">The user who creates the Yieldbroker connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="9bd81-127">이 역할은 준수 센터의 데이터 커넥터 페이지에서 Microsoft 365 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-127">This role is required to add connectors on the Data connectors page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="9bd81-128">기본적으로 이 역할은 역할 그룹의 역할 그룹에 할당되지 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9bd81-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="9bd81-129">사서함 가져오기 내보내기 역할을 조직의 조직 관리 역할 그룹에 추가할 수 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9bd81-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="9bd81-130">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="9bd81-131">자세한 내용은 "역할 [](/Exchange/permissions-exo/role-groups#create-role-groups) 그룹에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="9bd81-131">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-yieldbroker-connector"></a><span data-ttu-id="9bd81-132">1단계: Yieldbroker 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="9bd81-132">Step 1: Set up the Yieldbroker connector</span></span>

<span data-ttu-id="9bd81-133">첫 번째 단계는 준수  센터의 데이터 커넥터 페이지에 액세스하고 Microsoft 365 대한 커넥터를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for the Yieldbroker.</span></span>

1. <span data-ttu-id="9bd81-134">으로 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 이동한 다음 **데이터** 커넥터 &gt; **Yieldbroker를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9bd81-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** &gt; **Yieldbroker**.</span></span>

2. <span data-ttu-id="9bd81-135">**Yieldbroker** 제품 설명 페이지에서 새 커넥터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9bd81-135">On the **Yieldbroker** product description page, click **Add new connector**.</span></span>

3. <span data-ttu-id="9bd81-136">서비스 **약관 페이지에서** 동의를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9bd81-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="9bd81-137">커넥터를 식별하는 고유한 이름을 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="9bd81-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="9bd81-138">Merge1 계정에 로그인하여 커넥터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-yieldbroker-connector-on-the-veritas-merge1-site"></a><span data-ttu-id="9bd81-139">2단계: Veritas Merge1 사이트에서 Yieldbroker 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="9bd81-139">Step 2: Configure the Yieldbroker connector on the Veritas Merge1 site</span></span>

<span data-ttu-id="9bd81-140">두 번째 단계는 Merge1 사이트에서 Yieldbroker 커넥터를 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-140">The second step is to configure the Yieldbroker connector on the Merge1 site.</span></span> <span data-ttu-id="9bd81-141">Yieldbroker를 구성하는 방법에 대한 자세한 내용은 [Merge1 Third-Party Connectors User Guide를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Yieldbroker%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="9bd81-141">For information about how to configure the Yieldbroker, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Yieldbroker%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="9bd81-142">저장 및 & **마친** 후  준수 센터의 커넥터 마법사에 Microsoft 365 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="9bd81-143">3단계: 사용자 매핑 및 커넥터 설정 완료</span><span class="sxs-lookup"><span data-stu-id="9bd81-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="9bd81-144">사용자를 매핑하고 커넥터 설정을 완료하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-144">To map users and complete the connector setup, follow these steps:</span></span>

1. <span data-ttu-id="9bd81-145">Map **Yieldbroker users to Microsoft 365 페이지에서** 자동 사용자 매핑을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-145">On the **Map Yieldbroker users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="9bd81-146">Yieldbroker 항목에는 조직의 사용자에 대한 전자 메일 주소가 포함된 *Email이라는* 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-146">The Yieldbroker items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="9bd81-147">커넥터가 이 주소를 Microsoft 365 사용자 사서함으로 항목을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="9bd81-148">**다음을** 클릭하고 설정을 검토하고  데이터 커넥터 페이지로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-148">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-yieldbroker-connector"></a><span data-ttu-id="9bd81-149">4단계: Yieldbroker 커넥터 모니터링</span><span class="sxs-lookup"><span data-stu-id="9bd81-149">Step 4: Monitor the Yieldbroker connector</span></span>

<span data-ttu-id="9bd81-150">Yieldbroker 커넥터를 만든 후 준수 센터에서 커넥터 상태를 Microsoft 365 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-150">After you create the Yieldbroker connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="9bd81-151">으로 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="9bd81-152">커넥터 **탭을** 클릭한 다음 **Yieldbroker** 커넥터를 선택하여 커넥터에 대한 속성과 정보가 포함된 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-152">Click the **Connectors** tab and then select the **Yieldbroker** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="9bd81-153">원본이 있는 커넥터 상태  **아래에서** 로그 다운로드 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="9bd81-154">이 로그에는 Microsoft 클라우드로 가져온 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="9bd81-155">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="9bd81-155">Known issues</span></span>

- <span data-ttu-id="9bd81-156">현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="9bd81-157">더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9bd81-157">Support for larger items will be available at a later date.</span></span>