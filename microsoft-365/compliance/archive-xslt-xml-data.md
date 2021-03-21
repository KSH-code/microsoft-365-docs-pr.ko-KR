---
title: Microsoft 365에서 XSLT/XML 데이터를 보관할 커넥터 설정
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
description: 관리자는 Microsoft 365의 Globanet에서 XSLT/XML 데이터를 가져오고 보관하는 커넥터를 설정할 수 있습니다. 이 커넥터를 사용하면 Microsoft 365에서 타사 데이터 원본의 데이터를 보관할 수 있으므로 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용하여 조직의 타사 데이터를 관리할 수 있습니다.
ms.openlocfilehash: 097b523b6a1909f3f9575302fe11ad61a7558472
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921728"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data"></a><span data-ttu-id="050fc-104">XSLT/XML 데이터를 보관할 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="050fc-104">Set up a connector to archive XSLT/XML data</span></span>

<span data-ttu-id="050fc-105">Microsoft 365 규정 준수 센터의 Globanet 커넥터를 사용하여 웹 페이지 원본에서 Microsoft 365 조직의 사용자 사서함으로 데이터를 가져오고 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Web page source to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="050fc-106">Globanet은 XSLT(Extensible Style sheet Language Transformations)를 사용하여 XML 파일을 Microsoft 365로 가져올 수 있는 다른 파일 형식(예: HTML 또는 텍스트)으로 변환하여 파일을 빠르게 개발할 수 있는 [XSLT/XML](https://globanet.com/xslt-xml) 커넥터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-106">Globanet provides you with an [XSLT/XML connector](https://globanet.com/xslt-xml) that allows the rapid development of files created by using XSLT (Extensible Style sheet Language Transformations) to transform XML files into other file formats (such as HTML or text) that can be imported to Microsoft 365.</span></span> <span data-ttu-id="050fc-107">커넥터는 항목의 내용을 XSLT/XML 원본에서 전자 메일 메시지 형식으로 변환한 다음 변환된 항목을 Microsoft 365 사서함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-107">The connector converts the content of an item from the XSLT/XML source to an email message format and then imports the converted item to Microsoft 365 mailboxes.</span></span>

<span data-ttu-id="050fc-108">XSLT/XML 데이터를 사용자 사서함에 저장한 후 소송 보존, eDiscovery, 보존 정책 및 보존 레이블과 같은 Microsoft 365 규정 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-108">After XSLT/XML data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, and retention policies and retention labels.</span></span> <span data-ttu-id="050fc-109">XSLT/XML 커넥터를 사용하여 Microsoft 365에서 데이터를 가져오고 보관하면 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-109">Using an XSLT/XML connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-xsltxml-data"></a><span data-ttu-id="050fc-110">XSLT/XML 데이터 보관 개요</span><span class="sxs-lookup"><span data-stu-id="050fc-110">Overview of archiving XSLT/XML data</span></span>

<span data-ttu-id="050fc-111">다음 개요에서는 커넥터를 사용하여 Microsoft 365에서 XSLT/XML 원본 데이터를 보관하는 프로세스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-111">The following overview explains the process of using a connector to archive XSLT/XML source data in Microsoft 365.</span></span>

![XSLT/XML 데이터에 대한 보관 워크플로](../media/XSLT-XMLConnectorWorkflow.png)

1. <span data-ttu-id="050fc-113">조직은 XSLT/XML 원본과 함께 XSLT/XML 사이트를 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-113">Your organization works with the XSLT/XML source to set up and configure an XSLT/XML site.</span></span>

2. <span data-ttu-id="050fc-114">24시간마다 XSLT/XML 원본의 채팅 메시지가 Globanet Merge1 사이트에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-114">Once every 24 hours, chat messages from the XSLT/XML source are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="050fc-115">또한 커넥터는 콘텐츠를 전자 메일 메시지 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-115">The connector also converts the content to an email message format.</span></span>

3. <span data-ttu-id="050fc-116">Microsoft 365 규정 준수 센터에서 만드는 XSLT/XML 커넥터는 매일 Globanet Merge1 사이트에 연결하고 메시지를 Microsoft 클라우드의 보안 Azure Storage 위치로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-116">The XSLT/XML connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="050fc-117">커넥터는 3단계에 설명된 자동 사용자 매핑의 *Email* 속성 값을 사용하여 변환된 메시지 항목을 특정 사용자의 사서함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-117">The connector imports the converted message items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in Step 3.</span></span> <span data-ttu-id="050fc-118">받은 편지함 **폴더의 XSLT/XML이라는** 새 하위 폴더가 사용자 사서함에 만들어지며 메시지 항목을 해당 폴더로 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-118">A new subfolder in the Inbox folder named **XSLT/XML** is created in the user mailboxes, and the message items are imported to that folder.</span></span> <span data-ttu-id="050fc-119">이 커넥터는 Email 속성 값을 사용하여 이 *기능을* 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="050fc-120">모든 메시지에는 메시지 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-120">Every message contains this property, which is populated with the email address of every participant of the message.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="050fc-121">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="050fc-121">Before you begin</span></span>

- <span data-ttu-id="050fc-122">Microsoft 커넥터에 대한 Globanet Merge1 계정을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="050fc-123">이 계정을 만들하려면 [Globanet 고객 지원에 문의하세요.](https://globanet.com/contact-us/)</span><span class="sxs-lookup"><span data-stu-id="050fc-123">To create this account, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="050fc-124">1단계에서 커넥터를 만들 때 이 계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="050fc-125">1단계에서 XSLT/XML 커넥터를 만들고 3단계에서 완료하는 사용자는 Exchange Online의 사서함 가져오기 내보내기 역할에 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-125">The user who creates the XSLT/XML connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="050fc-126">이 역할은 Microsoft 365 규정 준수 센터의 데이터 커넥터 페이지에서 커넥터를 추가하는 데 필요합니다. </span><span class="sxs-lookup"><span data-stu-id="050fc-126">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="050fc-127">기본적으로 이 역할은 Exchange Online의 역할 그룹에 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-127">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="050fc-128">Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-128">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="050fc-129">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-129">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="050fc-130">자세한 내용은 "Exchange [](/Exchange/permissions-exo/role-groups#create-role-groups) Online에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="050fc-130">For more information, see the [Create role groups](/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-an-xsltxml-connector"></a><span data-ttu-id="050fc-131">1단계: XSLT/XML 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="050fc-131">Step 1: Set up an XSLT/XML connector</span></span>

<span data-ttu-id="050fc-132">첫 번째 단계는 Microsoft  365 규정 준수 센터에서 데이터 커넥터에 액세스하고 XSLT/XML 데이터에 대한 커넥터를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-132">The first step is to access to the **Data Connectors** in the Microsoft 365 compliance center and create a connector for XSLT/XML data.</span></span>

1. <span data-ttu-id="050fc-133">으로 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 이동한 다음 **데이터** 커넥터  >  **XSLT/XML을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="050fc-133">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **XSLT/XML**.</span></span>

2. <span data-ttu-id="050fc-134">**XSLT/XML** 제품 설명 페이지에서 새 커넥터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="050fc-134">On the **XSLT/XML** product description page, click **Add new connector**.</span></span>

3. <span data-ttu-id="050fc-135">서비스 **약관 페이지에서** 동의를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="050fc-135">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="050fc-136">커넥터를 식별하는 고유한 이름을 입력하고 다음 을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="050fc-136">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="050fc-137">Merge1 계정에 로그인하여 커넥터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-137">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-an-xsltxml-connector"></a><span data-ttu-id="050fc-138">2단계: XSLT/XML 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="050fc-138">Step 2: Configure an XSLT/XML connector</span></span>

<span data-ttu-id="050fc-139">두 번째 단계는 Merge1 사이트에서 XSLT/XML 커넥터를 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-139">The second step is to configure the XSLT/XML connector on the Merge1 site.</span></span> <span data-ttu-id="050fc-140">Globanet Merge1 사이트에서 XSLT/XML 커넥터를 구성하는 방법에 대한 자세한 내용은 [Merge1 Third-Party Connectors User Guide를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="050fc-140">For information about how to configure the XSLT/XML connector on the Globanet Merge1 site, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="050fc-141">저장 및 & **마친** 후  Microsoft 365 규정 준수 센터의 커넥터 마법사에 있는 사용자 매핑 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-141">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="050fc-142">3단계: 사용자 매핑 및 커넥터 설정 완료</span><span class="sxs-lookup"><span data-stu-id="050fc-142">Step 3: Map users and complete the connector setup</span></span>

1. <span data-ttu-id="050fc-143">사용자를 매핑하고 Microsoft 365 규정 준수 센터에서 커넥터 설정을 완료하려면 다음 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-143">To map users and complete the connector setup in the Microsoft 365 compliance center, follow the steps below:</span></span>

2. <span data-ttu-id="050fc-144">**XSLT/XML 사용자를 Microsoft 365** 사용자에 매핑 페이지에서 자동 사용자 매핑을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-144">On the **Map XSLT/XML users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="050fc-145">XSLT/XML 항목에는 조직의 사용자에 대한 전자 메일 주소가 포함된 *Email이라는* 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-145">The XSLT/XML items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="050fc-146">커넥터가 이 주소를 Microsoft 365 사용자와 연결하면 항목이 해당 사용자의 사서함으로 가져오기됩니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-146">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

3. <span data-ttu-id="050fc-147">**다음을** 클릭하고 설정을 검토하고  데이터 커넥터 페이지로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-147">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-xsltxml-connector"></a><span data-ttu-id="050fc-148">4단계: XSLT/XML 커넥터 모니터링</span><span class="sxs-lookup"><span data-stu-id="050fc-148">Step 4: Monitor the XSLT/XML connector</span></span>

<span data-ttu-id="050fc-149">XSLT/XML 커넥터를 만든 후 Microsoft 365 규정 준수 센터에서 커넥터 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-149">After you create the XSLT/XML connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="050fc-150">으로 [https://compliance.microsoft.com](https://compliance.microsoft.com) 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-150">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="050fc-151">커넥터 **탭을** 클릭한 다음 **XSLT/XML** 커넥터를 선택하여 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-151">Click the **Connectors** tab and then select the **XSLT/XML** connector to display the flyout page.</span></span> <span data-ttu-id="050fc-152">이 페이지에는 커넥터에 대한 속성과 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-152">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="050fc-153">원본이 있는 커넥터 상태  **아래에서** 로그 다운로드 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-153">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="050fc-154">이 로그에는 Microsoft 클라우드로 가져온 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-154">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="050fc-155">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="050fc-155">Known issues</span></span>

- <span data-ttu-id="050fc-156">현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-156">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="050fc-157">더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="050fc-157">Support for larger items will be available at a later date.</span></span>