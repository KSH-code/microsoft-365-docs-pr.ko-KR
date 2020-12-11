---
title: Microsoft 365에서 EML 데이터를 보관하는 커넥터 설정
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
description: 관리자는 Globanet에서 Microsoft 365로 EML 데이터를 가져오고 보관하는 커넥터를 설정할 수 있습니다. 이 커넥터를 사용하면 Microsoft 365에서 타사 데이터 원본의 데이터를 보관할 수 있습니다. 이 데이터를 보관한 후 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 준수 기능을 사용하여 타사 데이터를 관리할 수 있습니다.
ms.openlocfilehash: 7c8649565df4e08fbdbdaf9c1cba0d890eb54b52
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620445"
---
# <a name="set-up-a-connector-to-archive-eml-data"></a><span data-ttu-id="f1bac-105">EML 데이터를 보관할 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="f1bac-105">Set up a connector to archive EML data</span></span>

<span data-ttu-id="f1bac-106">Microsoft 365 규정 준수 센터의 Globanet 커넥터를 사용하여 MICROSOFT 365 조직의 사용자 사서함에 EML 데이터를 가져오고 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive EML data to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="f1bac-107">EML은 파일에 저장된 전자 메일 메시지의 파일 확장명입니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-107">EML is the file extension for an email message saved to a file.</span></span> <span data-ttu-id="f1bac-108">커넥터는 항목의 내용을 원본 형식에서 전자 메일 메시지 형식으로 변환한 다음 항목을 사용자 사서함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-108">The connector converts the content of an item from the source format to an email message format and then imports the item to a user mailbox.</span></span>

<span data-ttu-id="f1bac-109">EML 메시지가 사용자 사서함에 저장되고 나면 소송 보존, eDiscovery, 보존 정책 및 보존 레이블과 같은 Microsoft 365 규정 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-109">After EML messages are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, and retention policies and retention labels.</span></span> <span data-ttu-id="f1bac-110">EML 커넥터를 사용하여 Microsoft 365에서 데이터를 가져오고 보관하면 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-110">Using an EML connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-eml-data"></a><span data-ttu-id="f1bac-111">EML 데이터 보관 개요</span><span class="sxs-lookup"><span data-stu-id="f1bac-111">Overview of archiving EML data</span></span>

<span data-ttu-id="f1bac-112">다음 개요에서는 커넥터를 사용하여 Microsoft 365에서 EML 데이터를 보관하는 프로세스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-112">The following overview explains the process of using a connector to archive EML data in Microsoft 365.</span></span>

![EML 데이터에 대한 보관 워크플로](../media/EMLConnectorWorkflow.png)

1. <span data-ttu-id="f1bac-114">조직은 EML 원본과 함께 EML 사이트를 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-114">Your organization works with the EML source to set up and configure an EML site.</span></span>

2. <span data-ttu-id="f1bac-115">24시간마다 한 번씩 EML 원본의 콘텐츠 항목이 Globanet Merge1 사이트에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-115">Once every 24 hours, content items from the EML source are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="f1bac-116">이 프로세스 중에 EML 파일의 콘텐츠가 전자 메일 메시지 형식으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-116">During this process, the content of an EML file is converted to an email message format.</span></span>

3. <span data-ttu-id="f1bac-117">Microsoft 365 규정 준수 센터에서 만든 EML 커넥터는 매일 Globanet Merge1 사이트에 연결하고 메시지를 Microsoft 클라우드의 보안 Azure Storage 위치로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-117">The EML connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="f1bac-118">커넥터는 3단계에 설명된 자동 사용자 매핑 프로세스의 *Email* 속성 값을 사용하여 변환된 메시지 항목을 특정 사용자의 사서함으로 [가져올 수 있습니다.](#step-3-map-users-and-complete-the-connector-setup)</span><span class="sxs-lookup"><span data-stu-id="f1bac-118">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping process that's described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="f1bac-119">이 프로세스 중에 받은 편지함 폴더 **EML이라는** 하위 폴더가 사용자 사서함에 만들어지며 EML 항목을 해당 폴더로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-119">During this process, a subfolder in the Inbox folder named **EML** is created in the user mailboxes, and the EML items are imported to that folder.</span></span> <span data-ttu-id="f1bac-120">커넥터는 Email 속성 값을 사용하여 항목을 가져올 사서함을 결정할 *수* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="f1bac-121">모든 메시지에는 콘텐츠 항목의 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-121">Every message contains this property, which is populated with the email address of every participant of the content item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="f1bac-122">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="f1bac-122">Before you begin</span></span>

- <span data-ttu-id="f1bac-123">Microsoft 커넥터에 대한 Globanet Merge1 계정을 만드시다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="f1bac-124">계정을 만들 경우 [Globanet 고객](https://globanet.com/ms-connectors-contact)지원에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="f1bac-124">To create an account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact).</span></span> <span data-ttu-id="f1bac-125">1단계에서 커넥터를 만들 때 이 계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-125">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="f1bac-126">1단계에서 EML 커넥터를 만들고 3단계에서 완료하는 사용자는 Exchange Online의 사서함 가져오기 내보내기 역할에 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-126">The user who creates the EML connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="f1bac-127">이 역할은 Microsoft 365 규정 준수 센터의 데이터 커넥터 페이지에서 커넥터를 추가하는 데 필요합니다. </span><span class="sxs-lookup"><span data-stu-id="f1bac-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="f1bac-128">기본적으로 이 역할은 Exchange Online의 역할 그룹에 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-128">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="f1bac-129">Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="f1bac-130">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="f1bac-131">자세한 내용은 "Exchange [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Online에서 [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서에서 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f1bac-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-an-eml-connector"></a><span data-ttu-id="f1bac-132">1단계: EML 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="f1bac-132">Step 1: Set up an EML Connector</span></span>

<span data-ttu-id="f1bac-133">첫 번째 단계는 Microsoft  365 규정 준수 센터의 데이터 커넥터 페이지에 액세스하고 EML 데이터에 대한 커넥터를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-133">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for EML data.</span></span>

1. <span data-ttu-id="f1bac-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click Data **connectors**  >  **EML.**</span><span class="sxs-lookup"><span data-stu-id="f1bac-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **EML**.</span></span>

2. <span data-ttu-id="f1bac-135">**EML 제품** 설명 페이지에서 커넥터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f1bac-135">On the **EML** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="f1bac-136">서비스 약관 **페이지에서** 수락을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f1bac-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="f1bac-137">커넥터를 식별하는 고유한 이름을 입력하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="f1bac-137">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="f1bac-138">Merge1 계정에 로그인하여 커넥터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-eml-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="f1bac-139">2단계: Globanet Merge1 사이트에서 EML 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="f1bac-139">Step 2: Configure the EML connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="f1bac-140">두 번째 단계는 Globanet Merge1 사이트에서 EML 커넥터를 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-140">The second step is to configure the EML connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="f1bac-141">EML 커넥터 구성에 대한 자세한 내용은 Merge1 타사 커넥터 [사용자 가이드를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20EML%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="f1bac-141">For information about configuring  the EML connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20EML%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="f1bac-142">저장 **&** 마친 후 Microsoft  365 준수 센터의 커넥터 마법사에 있는 사용자 매핑 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="f1bac-143">3단계: 사용자 매핑 및 커넥터 설정 완료</span><span class="sxs-lookup"><span data-stu-id="f1bac-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="f1bac-144">사용자를 매핑하고 Microsoft 365 규정 준수 센터에서 커넥터 설정을 완료하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-144">To map users and complete the connector setup in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="f1bac-145">외부 사용자를 **Microsoft 365** 사용자에 매핑 페이지에서 자동 사용자 매핑을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-145">On the **Map external users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="f1bac-146">EML 원본 항목에는 조직의 사용자에 대한 전자 메일 주소가 포함된 *Email이라는* 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-146">The EML source items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="f1bac-147">커넥터가 이 주소를 Microsoft 365 사용자와 연결하면 EML 항목이 해당 사용자의 사서함으로 가져오기됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-147">If the connector can associate this address with a Microsoft 365 user, the EML items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="f1bac-148">다음을 **클릭하고** 설정을 검토한 다음  데이터 커넥터 페이지로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-148">Click **Next**, review your settings, and then go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-eml-connector"></a><span data-ttu-id="f1bac-149">4단계: EML 커넥터 모니터링</span><span class="sxs-lookup"><span data-stu-id="f1bac-149">Step 4: Monitor the EML connector</span></span>

<span data-ttu-id="f1bac-150">EML 커넥터를 만든 후 Microsoft 365 준수 센터에서 커넥터 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-150">After you create the EML connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="f1bac-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span><span class="sxs-lookup"><span data-stu-id="f1bac-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="f1bac-152">커넥터 **탭을** 클릭한 다음 **EML** 커넥터를 선택하여 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-152">Click the **Connectors** tab and then select the **EML** connector to display the flyout page.</span></span> <span data-ttu-id="f1bac-153">이 페이지에는 커넥터에 대한 속성과 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-153">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="f1bac-154">원본이 **있는 커넥터** 상태  아래에서 다운로드 로그 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-154">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="f1bac-155">이 로그에는 Microsoft 클라우드로 가져온 데이터에 대한 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-155">This log contains information about the data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="f1bac-156">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="f1bac-156">Known issues</span></span>

- <span data-ttu-id="f1bac-157">현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-157">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="f1bac-158">더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1bac-158">Support for larger items will be available at a later date.</span></span>
