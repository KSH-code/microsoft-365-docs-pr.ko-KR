---
title: 팩트 집합 데이터를 보관할 커넥터를 Microsoft 365
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
description: 17a-4 FactSet DataParser 커넥터를 설정하고 사용하여 17a-4 FactSet DataParser 커넥터에서 FactSet 데이터를 가져오고 보관하는 Microsoft 365.
ms.openlocfilehash: 26beead657618dc3b33a11d8b6202c914a9c49bc
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454520"
---
# <a name="set-up-a-connector-to-archive-factset-data"></a><span data-ttu-id="2ccb3-103">FactSet 데이터를 보관할 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="2ccb3-103">Set up a connector to archive FactSet data</span></span>

<span data-ttu-id="2ccb3-104">17a-4 LLC의 [FactSet DataParser를](https://www.17a-4.com/factset-dataparser/) 사용하여 FactSet 플랫폼에서 조직의 사용자 사서함으로 데이터를 Microsoft 365 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-104">Use the [FactSet DataParser](https://www.17a-4.com/factset-dataparser/) from 17a-4 LLC to import and archive data from the FactSet platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="2ccb3-105">DataParser에는 타사 데이터 원본의 항목을 캡처하고 해당 항목을 가져오도록 구성된 FactSet 커넥터가 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-105">The DataParser includes a FactSet connector that's configured to capture items from a third-party data source and import those items to Microsoft 365.</span></span> <span data-ttu-id="2ccb3-106">FactSet DataParser 커넥터는 FactSet 데이터를 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 전자 메일 메시지의 사용자 사서함으로 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-106">The FactSet DataParser connector converts FactSet data to an email message format and then imports those items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="2ccb3-107">FactSet 데이터를 사용자 사서함에 저장한 후 소송 보존, eDiscovery Microsoft 365 보존 정책 및 보존 레이블, 통신 준수와 같은 Microsoft 365 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-107">After FactSet data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="2ccb3-108">FactSet 커넥터를 사용하여 조직의 데이터 가져오기 및 보관을 Microsoft 365 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-108">Using a FactSet connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-factset-data"></a><span data-ttu-id="2ccb3-109">FactSet 데이터 보관 개요</span><span class="sxs-lookup"><span data-stu-id="2ccb3-109">Overview of archiving FactSet data</span></span>

<span data-ttu-id="2ccb3-110">다음 개요에서는 데이터 커넥터를 사용하여 데이터 커넥터에서 FactSet 데이터를 보관하는 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-110">The following overview explains the process of using a data connector to archive FactSet data in Microsoft 365.</span></span>

![17a-4의 FactSet 데이터에 대한 보관 워크플로](../media/FactSetDataParserConnectorWorkflow.png)

1. <span data-ttu-id="2ccb3-112">조직은 17a-4와 함께 FactSet DataParser를 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-112">Your organization works with 17a-4 to set up and configure the FactSet DataParser.</span></span>

2. <span data-ttu-id="2ccb3-113">FactSet 항목은 정기적으로 DataParser에 의해 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-113">On a regular basis, FactSet items are collected by the DataParser.</span></span> <span data-ttu-id="2ccb3-114">또한 DataParser는 메시지 내용을 전자 메일 메시지 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-114">The DataParser also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="2ccb3-115">조직에서 만드는 FactSet DataParser 커넥터는 Microsoft 365 규정 준수 센터 연결하고 메시지를 Microsoft 클라우드의 보안 Azure Storage 위치로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-115">The FactSet DataParser connector that you create in the Microsoft 365 compliance center connects to DataParser and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="2ccb3-116">받은 편지함 **폴더의 FactSet DataParser라는** 하위 폴더가 사용자 사서함에 만들어지며 FactSet 항목을 해당 폴더로 가져오게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-116">A subfolder in the Inbox folder named **FactSet DataParser** is created in the user mailboxes, and the FactSet items are imported to that folder.</span></span> <span data-ttu-id="2ccb3-117">커넥터는 Email 속성 값을 사용하여 항목을 가져올 사서함을 결정할 *수* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-117">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="2ccb3-118">모든 FactSet 항목에는 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-118">Every FactSet item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-set-up-a-connector"></a><span data-ttu-id="2ccb3-119">커넥터를 설정하기 전에</span><span class="sxs-lookup"><span data-stu-id="2ccb3-119">Before you set up a connector</span></span>

- <span data-ttu-id="2ccb3-120">Microsoft 커넥터에 대한 DataParser 계정을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-120">Create a DataParser account for Microsoft connectors.</span></span> <span data-ttu-id="2ccb3-121">이 작업을 위해 [17a-4 LLC에 문의합니다.](https://www.17a-4.com/contact/)</span><span class="sxs-lookup"><span data-stu-id="2ccb3-121">To do this, contact [17a-4 LLC](https://www.17a-4.com/contact/).</span></span> <span data-ttu-id="2ccb3-122">1단계에서 커넥터를 만들 때 이 계정에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-122">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="2ccb3-123">1단계에서 FactSet DataParser 커넥터를 만들고 3단계에서 완료하는 사용자는 2단계에서 사서함 가져오기 내보내기 역할에 할당해야 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-123">The user who creates the FactSet DataParser connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="2ccb3-124">이 역할은 서버의 데이터  커넥터 페이지에서 커넥터를 추가하는 Microsoft 365 규정 준수 센터.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-124">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="2ccb3-125">기본적으로 이 역할은 역할 그룹의 역할 그룹에 할당되지 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-125">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="2ccb3-126">사서함 가져오기 내보내기 역할을 조직의 조직 관리 역할 그룹에 추가할 수 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-126">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="2ccb3-127">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-127">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="2ccb3-128">자세한 내용은 "역할 [](/Exchange/permissions-exo/role-groups#create-role-groups) 그룹에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-128">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-a-factset-dataparser-connector"></a><span data-ttu-id="2ccb3-129">1단계: FactSet DataParser 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="2ccb3-129">Step 1: Set up a FactSet DataParser connector</span></span>

<span data-ttu-id="2ccb3-130">첫 번째 단계는 2단계에서 데이터 커넥터 페이지에 액세스하고 Microsoft 365 규정 준수 센터 팩트 집합 데이터에 대한 17a-4 커넥터를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-130">The first step is to access to the Data connectors page in the Microsoft 365 compliance center and create a 17a-4 connector for FactSet data.</span></span>

1. <span data-ttu-id="2ccb3-131">으로 <https://compliance.microsoft.com> 이동한 다음 **데이터** 커넥터  >  **FactSet DataParser 를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2ccb3-131">Go to <https://compliance.microsoft.com> and then click **Data connectors** > **FactSet DataParser**.</span></span>

2. <span data-ttu-id="2ccb3-132">**FactSet DataParser** 제품 설명 페이지에서 커넥터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2ccb3-132">On the **FactSet DataParser** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="2ccb3-133">서비스 **약관 페이지에서** 동의를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2ccb3-133">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="2ccb3-134">커넥터를 식별하는 고유한 이름을 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="2ccb3-134">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="2ccb3-135">17a-4 계정에 로그인하고 FactSet DataParser 연결 마법사의 단계를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-135">Sign in to your 17a-4 account and complete the steps in the FactSet DataParser connection wizard.</span></span>

## <a name="step-2-configure-the-factset-dataparser-connector"></a><span data-ttu-id="2ccb3-136">2단계: FactSet DataParser 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="2ccb3-136">Step 2: Configure the FactSet DataParser connector</span></span>

<span data-ttu-id="2ccb3-137">17a-4 지원에서 FactSet DataParser 커넥터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-137">Work with 17a-4 Support to configure the FactSet DataParser connector.</span></span>

## <a name="step-3-map-users"></a><span data-ttu-id="2ccb3-138">3단계: 사용자 매핑</span><span class="sxs-lookup"><span data-stu-id="2ccb3-138">Step 3: Map users</span></span>

<span data-ttu-id="2ccb3-139">FactSet DataParser 커넥터는 데이터를 전자 메일로 가져오기 전에 Microsoft 365 전자 메일 주소에 자동으로 Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-139">The FactSet DataParser connector will automatically map users to their Microsoft 365 email addresses before importing data to Microsoft 365.</span></span>

## <a name="step-4-monitor-the-factset-dataparser-connector"></a><span data-ttu-id="2ccb3-140">4단계: FactSet DataParser 커넥터 모니터링</span><span class="sxs-lookup"><span data-stu-id="2ccb3-140">Step 4: Monitor the FactSet DataParser connector</span></span>

<span data-ttu-id="2ccb3-141">FactSet DataParser 커넥터를 만든 후 연결선의 커넥터 상태를 볼 수 Microsoft 365 규정 준수 센터.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-141">After you create a FactSet DataParser connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="2ccb3-142">으로 <https://compliance.microsoft.com> 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-142">Go to <https://compliance.microsoft.com> and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="2ccb3-143">커넥터 **탭을** 클릭한 다음 만든 FactSet DataParser 커넥터를 선택하여 커넥터에 대한 속성과 정보가 포함된 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-143">Click the **Connectors** tab and then select the FactSet DataParser connector that you created to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="2ccb3-144">원본이 있는 커넥터 상태  **아래에서** 로그 다운로드 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-144">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="2ccb3-145">이 로그에는 Microsoft 클라우드로 가져온 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-145">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="2ccb3-146">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="2ccb3-146">Known issues</span></span>

<span data-ttu-id="2ccb3-147">현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-147">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="2ccb3-148">더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2ccb3-148">Support for larger items will be available at a later date.</span></span>
