---
title: 커넥터를 설정하여 SQL 데이터를 Microsoft 365
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
description: DataParser 커넥터를 사용하여 17a-4 SQL 설정하고 사용하여 SQL 데이터를 가져오고 보관하는 Microsoft 365.
ms.openlocfilehash: 51fd433ad072ba5afe0b314d7b61041728337240
ms.sourcegitcommit: 410f6e1c6cf53c3d9013b89d6e0b40a050ee9cad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2021
ms.locfileid: "53137670"
---
# <a name="set-up-a-connector-to-archive-sql-data-preview"></a><span data-ttu-id="dc333-103">데이터 보관 커넥터 설정(SQL 미리 보기)</span><span class="sxs-lookup"><span data-stu-id="dc333-103">Set up a connector to archive SQL data (preview)</span></span>

<span data-ttu-id="dc333-104">17a-4 LLC의 SQL [DataParser를](https://www.17a-4.com/sql-dataparser/) 사용하여 SQL 데이터베이스의 데이터를 Microsoft 365 사서함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-104">Use the [SQL DataParser](https://www.17a-4.com/sql-dataparser/) from 17a-4 LLC to import and archive data from a SQL database to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="dc333-105">DataParser에는 타사 SQL 원본의 항목을 캡처하고 해당 항목을 가져오도록 구성된 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc333-105">The DataParser includes a SQL connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="dc333-106">이 SQL DataParser 커넥터는 SQL 데이터를 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 전자 메일 메시지의 사용자 사서함으로 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc333-106">The SQL DataParser connector converts SQL data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="dc333-107">사용자 SQL 저장한 후 소송 보존, eDiscovery Microsoft 365 보존 정책 및 보존 레이블, 통신 준수와 같은 Microsoft 365 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-107">After SQL data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="dc333-108">SQL 커넥터를 사용하여 조직의 데이터 가져오기 및 보관을 Microsoft 365 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-108">Using a SQL connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-sql-data"></a><span data-ttu-id="dc333-109">보관 데이터 SQL 개요</span><span class="sxs-lookup"><span data-stu-id="dc333-109">Overview of archiving SQL data</span></span>

<span data-ttu-id="dc333-110">다음 개요에서는 데이터 커넥터를 사용하여 데이터 커넥터를 사용하여 SQL 데이터를 보관하는 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc333-110">The following overview explains the process of using a data connector to archive SQL data in Microsoft 365.</span></span>

![17a-SQL 데이터를 보관하는 워크플로](../media/SQLDatabaseDataParserConnectorWorkflow.png)

1. <span data-ttu-id="dc333-112">조직은 17a-4와 함께 작업하여 DataParser를 SQL 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-112">Your organization works with 17a-4 to set up and configure the SQL DataParser.</span></span>

2. <span data-ttu-id="dc333-113">정기적으로 SQL DataParser에서 항목을 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-113">On a regular basis, SQL items are collected by the DataParser.</span></span> <span data-ttu-id="dc333-114">또한 DataParser는 메시지 내용을 전자 메일 메시지 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="dc333-115">SQL 만든 Microsoft 365 규정 준수 센터 DataParser 커넥터는 DataParser에 연결하고 메시지를 Microsoft 클라우드의 보안 Azure Storage 위치로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-115">The SQL DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="dc333-116">사용자 사서함에 SQL **DataParser라는** 받은 편지함 폴더의 하위 폴더가 만들어지며 SQL 폴더로 가져오기됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-116">A subfolder in the Inbox folder named **SQL DataParser** is created in the user mailboxes, and the SQL items are imported to that folder.</span></span> <span data-ttu-id="dc333-117">커넥터는 Email 속성 값을 사용하여 항목을 가져올 사서함을 결정할 *수* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="dc333-118">모든 SQL 항목에는 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-118">Every SQL item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="dc333-119">커넥터를 설정하기 전에</span><span class="sxs-lookup"><span data-stu-id="dc333-119">Before you set up a connector</span></span>

- <span data-ttu-id="dc333-120">Microsoft 커넥터에 대한 DataParser 계정을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="dc333-121">이 작업을 위해 [17a-4 LLC에 문의합니다.](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="dc333-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="dc333-122">1단계에서 커넥터를 만들 때 이 계정에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="dc333-123">1단계에서 SQL DataParser 커넥터를 만들고 3단계에서 완료하는 사용자는 2단계에서 사서함 가져오기 내보내기 역할에 할당해야 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dc333-123">The user who creates the SQL DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="dc333-124">이 역할은 서버의 데이터  커넥터 페이지에서 커넥터를 추가하는 Microsoft 365 규정 준수 센터.</span><span class="sxs-lookup"><span data-stu-id="dc333-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="dc333-125">기본적으로 이 역할은 역할 그룹의 역할 그룹에 할당되지 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dc333-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="dc333-126">사서함 가져오기 내보내기 역할을 조직의 조직 관리 역할 그룹에 추가할 수 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dc333-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="dc333-127">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="dc333-128">자세한 내용은 "역할 [](/Exchange/permissions-exo/role-groups#create-role-groups) 그룹에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dc333-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-sql-dataparser-connector"></a><span data-ttu-id="dc333-129">1단계: DataParser SQL 설정</span><span class="sxs-lookup"><span data-stu-id="dc333-129">Step 1: Set up a SQL DataParser connector</span></span>

<span data-ttu-id="dc333-130">첫 번째 단계는 서버의 데이터 커넥터 페이지에 액세스하고 Microsoft 365 규정 준수 센터 17a-4 커넥터를 SQL 것입니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for SQL data.</span></span>

1. <span data-ttu-id="dc333-131">으로 이동한 다음 <https://compliance.microsoft.com> **DataParser에서**  >  **데이터 SQL 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dc333-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **SQL DataParser**.</span></span>

2. <span data-ttu-id="dc333-132">**DataParser SQL** 설명 페이지에서 커넥터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dc333-132">On the **SQL DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="dc333-133">서비스 **약관 페이지에서** 동의를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dc333-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="dc333-134">커넥터를 식별하는 고유한 이름을 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="dc333-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="dc333-135">17a-4 계정에 로그인하고 DataParser 연결 마법사의 SQL 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-135">Sign in to your 17a-4 account and complete the steps in the SQL DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-sql-dataparser-connector"></a><span data-ttu-id="dc333-136">2단계: SQL DataParser 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="dc333-136">Step 2: Configure the SQL DataParser connector</span></span>

<span data-ttu-id="dc333-137">17a-4 지원에서 데이터 SQL 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-137">Work with 17a-4 Support to configure the SQL DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="dc333-138">3단계: 사용자 매핑</span><span class="sxs-lookup"><span data-stu-id="dc333-138">Step 3: Map users</span></span>

<span data-ttu-id="dc333-139">이 SQL DataParser 커넥터는 데이터를 가져오기 전에 Microsoft 365 전자 메일 주소에 사용자를 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="dc333-139">The SQL DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-sql-dataparser-connector"></a><span data-ttu-id="dc333-140">4단계: 데이터 SQL 모니터링</span><span class="sxs-lookup"><span data-stu-id="dc333-140">Step 4: Monitor the SQL DataParser connector</span></span>

<span data-ttu-id="dc333-141">DataParser SQL 만들면 연결선의 커넥터 상태를 볼 수 Microsoft 365 규정 준수 센터.</span><span class="sxs-lookup"><span data-stu-id="dc333-141">After you create a SQL DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="dc333-142">으로 <https://compliance.microsoft.com> 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="dc333-143">커넥터 **탭을** 클릭한 다음 만든 SQL DataParser 커넥터를 선택하여 커넥터에 대한 속성과 정보가 포함된 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-143">Click the **Connectors** tab and then select the SQL DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="dc333-144">원본이 있는 커넥터 상태  **아래에서** 로그 다운로드 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="dc333-145">이 로그에는 Microsoft 클라우드로 가져온 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="dc333-146">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="dc333-146">Known issues</span></span>

<span data-ttu-id="dc333-147">현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="dc333-148">더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dc333-148">Support for larger items will be available at a later date.</span></span>
