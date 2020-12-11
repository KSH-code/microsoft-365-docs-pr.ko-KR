---
title: Microsoft 365에서 CellTrust 데이터를 보관할 커넥터 설정
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
description: 관리자는 Globanet에서 Microsoft 365로 CellTrust 데이터를 가져오고 보관하는 커넥터를 설정할 수 있습니다. 이 커넥터를 사용하면 Microsoft 365에서 타사 데이터 원본의 데이터를 보관할 수 있습니다. 이 데이터를 보관한 후 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 준수 기능을 사용하여 타사 데이터를 관리할 수 있습니다.
ms.openlocfilehash: 990f52eb48fcf031bda3c9f17884ff3d384afc55
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620489"
---
# <a name="set-up-a-connector-to-archive-celltrust-data"></a><span data-ttu-id="103ef-105">CellTrust 데이터를 보관할 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="103ef-105">Set up a connector to archive CellTrust data</span></span>

<span data-ttu-id="103ef-106">Microsoft 365 규정 준수 센터의 Globanet 커넥터를 사용하여 CellTrust 플랫폼에서 Microsoft 365 조직의 사용자 사서함으로 데이터를 가져오고 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the CellTrust platform to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="103ef-107">Globanet은 타사 데이터 원본에서 항목을 캡처하고(정기적으로) 해당 항목을 Microsoft 365로 가져오도록 구성된 [CellTrust](https://globanet.com/celltrust/) 커넥터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-107">Globanet provides a [CellTrust](https://globanet.com/celltrust/) connector that's configured to capture items from the third-party data source (on a regular basis) and import those items to Microsoft 365.</span></span> <span data-ttu-id="103ef-108">커넥터는 CellTrust 계정에서 전자 메일 메시지 형식으로 SMS 메시지의 내용을 변환한 다음 이러한 항목을 Microsoft 365의 사용자 사서함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-108">The connector converts the content of SMS messages from CellTrust accounts to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="103ef-109">CellTrust 데이터가 사용자 사서함에 저장되고 나면 소송 보존, eDiscovery, 보존 정책 및 보존 레이블, 통신 준수와 같은 Microsoft 365 규정 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-109">After CellTrust data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies and retention labels, and communication compliance.</span></span> <span data-ttu-id="103ef-110">CellTrust 커넥터를 사용하여 Microsoft 365에서 데이터를 가져오고 보관하면 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-110">Using a CellTrust connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-celltrust-data"></a><span data-ttu-id="103ef-111">CellTrust 데이터 보관 개요</span><span class="sxs-lookup"><span data-stu-id="103ef-111">Overview of archiving CellTrust data</span></span>

<span data-ttu-id="103ef-112">다음 개요에서는 커넥터를 사용하여 Microsoft 365에서 CellTrust 데이터를 보관하는 프로세스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-112">The following overview explains the process of using a connector to archive CellTrust data in Microsoft 365.</span></span>

![CellTrust 데이터에 대한 보관 워크플로](../media/CellTrustConnectorWorkflow.png)

1. <span data-ttu-id="103ef-114">조직은 CellTrust와 함께 CellTrust 사이트를 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-114">Your organization works with CellTrust to set up and configure a CellTrust site.</span></span>

2. <span data-ttu-id="103ef-115">24시간마다 CellTrust 항목이 Globanet Merge1 사이트에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-115">Once every 24 hours, CellTrust items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="103ef-116">또한 커넥터는 메시지 내용을 전자 메일 메시지 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-116">The connector also converts the content of a message to an email message format.</span></span>

3. <span data-ttu-id="103ef-117">Microsoft 365 규정 준수 센터에서 만든 CellTrust 커넥터는 매일 Globanet Merge1 사이트에 연결하고 메시지를 Microsoft 클라우드의 보안 Azure Storage 위치로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-117">The CellTrust connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="103ef-118">커넥터가 [3단계에서](#step-3-map-users-and-complete-the-connector-setup)설명한 *Email* 속성 값을 사용하여 항목을 특정 사용자의 사서함으로 가져오는 자동 사용자 매핑입니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-118">The automatic user mapping as connector imports items to the mailboxes of specific users by using the value of the *Email* property of the described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="103ef-119">받은 편지함 폴더 **CellTrust라는** 하위 폴더가 사용자 사서함에 만들어지며 메시지 항목을 해당 폴더로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-119">A subfolder in the Inbox folder named **CellTrust** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="103ef-120">커넥터는 Email 속성 값을 사용하여 항목을 가져올 사서함을 결정할 *수* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="103ef-121">모든 CellTrust 항목에는 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-121">Every CellTrust item contains this property, which is populated with the email address of every participant.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="103ef-122">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="103ef-122">Before you begin</span></span>

- <span data-ttu-id="103ef-123">Microsoft 커넥터에 대한 Merge1 계정을 만드시다.</span><span class="sxs-lookup"><span data-stu-id="103ef-123">Create a Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="103ef-124">계정을 만들 경우 [Globanet 고객](https://globanet.com/contact-us/)지원에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="103ef-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="103ef-125">1단계에서 커넥터를 만들 때 이 계정에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="103ef-126">1단계에서 CellTrust 커넥터를 만들고 3단계에서 완료하는 사용자는 Exchange Online의 사서함 가져오기 내보내기 역할에 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-126">The user who creates the CellTrust connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="103ef-127">이 역할은 Microsoft 365 규정 준수 센터의 데이터 커넥터 페이지에서 커넥터를 추가하는 데 필요합니다. </span><span class="sxs-lookup"><span data-stu-id="103ef-127">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="103ef-128">기본적으로 이 역할은 Exchange Online의 역할 그룹에 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-128">By default, this role is not assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="103ef-129">Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-129">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="103ef-130">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-130">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="103ef-131">자세한 내용은 "Exchange [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Online에서 [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서에서 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="103ef-131">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-celltrust-connector"></a><span data-ttu-id="103ef-132">1단계: CellTrust 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="103ef-132">Step 1: Set up the CellTrust connector</span></span>

<span data-ttu-id="103ef-133">첫 번째 단계는 Microsoft 365 규정 준수 센터에서 **데이터** 커넥터에 액세스하고 CellTrust 데이터에 대한 커넥터를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-133">The first step is to access to the **Data Connectors** in the Microsoft 365 compliance center and create a connector for CellTrust data.</span></span>

1. <span data-ttu-id="103ef-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click Data **connectors** \> **CellTrust.**</span><span class="sxs-lookup"><span data-stu-id="103ef-134">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** \> **CellTrust**.</span></span>

2. <span data-ttu-id="103ef-135">**CellTrust 제품 설명** 페이지에서 커넥터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="103ef-135">On the **CellTrust** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="103ef-136">서비스 약관 **페이지에서** 수락을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="103ef-136">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="103ef-137">커넥터를 식별하는 고유한 이름을 입력하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="103ef-137">Enter a unique name that identifies the connector and then click **Next**.</span></span>

5. <span data-ttu-id="103ef-138">Merge1 계정에 로그인하여 커넥터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-138">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-celltrust-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="103ef-139">2단계: Globanet Merge1 사이트에서 CellTrust 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="103ef-139">Step 2: Configure the CellTrust connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="103ef-140">두 번째 단계는 Globanet Merge1 사이트에서 CellTrust 커넥터를 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-140">The second step is to configure the CellTrust connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="103ef-141">CellTrust 커넥터를 구성하는 방법에 대한 자세한 내용은 [Merge1 Third-Party Connectors 사용자 가이드를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20CellTrust%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="103ef-141">For information about how to configure the CellTrust connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20CellTrust%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="103ef-142">저장 **&** 마친 후 Microsoft  365 준수 센터의 커넥터 마법사에 있는 사용자 매핑 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-142">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="103ef-143">3단계: 사용자 매핑 및 커넥터 설정 완료</span><span class="sxs-lookup"><span data-stu-id="103ef-143">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="103ef-144">사용자를 매핑하고 Microsoft 365 규정 준수 센터에서 설정된 커넥터를 완료하기 위해 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-144">To map users and complete the connector set up in the Microsoft 365 compliance center, follow these steps:</span></span>

1. <span data-ttu-id="103ef-145">**CellTrust 사용자를 Microsoft 365** 사용자로 매핑 페이지에서 자동 사용자 매핑을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-145">On the **Map CellTrust users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="103ef-146">CellTrust 항목에는 조직의 사용자에 대한 전자 메일 주소가 포함된 *Email이라는* 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-146">The CellTrust items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="103ef-147">커넥터가 이 주소를 Microsoft 365 사용자와 연결하면 항목이 해당 사용자의 사서함으로 가져오기됩니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-147">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="103ef-148">다음을 **클릭하고** 설정을 검토하고  데이터 커넥터 페이지로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-148">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-celltrust-connector"></a><span data-ttu-id="103ef-149">4단계: CellTrust 커넥터 모니터링</span><span class="sxs-lookup"><span data-stu-id="103ef-149">Step 4: Monitor the CellTrust connector</span></span>

<span data-ttu-id="103ef-150">CellTrust 커넥터를 만든 후 Microsoft 365 규정 준수 센터에서 커넥터 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-150">After you create the CellTrust connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="103ef-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span><span class="sxs-lookup"><span data-stu-id="103ef-151">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="103ef-152">커넥터 **탭을** 클릭한 다음 **CellTrust** 커넥터를 선택하여 커넥터에 대한 속성과 정보가 포함된 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-152">Click the **Connectors** tab and then select the **CellTrust** connector to display the flyout page, which contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="103ef-153">원본이 **있는 커넥터** 상태  아래에서 다운로드 로그 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="103ef-154">이 로그에는 Microsoft 클라우드로 가져온 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="103ef-155">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="103ef-155">Known issues</span></span>

- <span data-ttu-id="103ef-156">현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="103ef-157">더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="103ef-157">Support for larger items will be available at a later date.</span></span>
