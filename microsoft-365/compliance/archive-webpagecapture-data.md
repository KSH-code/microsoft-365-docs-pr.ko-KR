---
title: Microsoft 365에서 웹 페이지 데이터를 보관할 커넥터 설정
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
description: 관리자는 Microsoft 365의 Globanet에서 웹 페이지 캡처 데이터를 가져오고 보관하는 커넥터를 설정할 수 있습니다. 이 커넥터를 사용하면 Microsoft 365의 타사 데이터 원본에서 데이터를 보관할 수 있으므로 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용하여 조직의 타사 데이터를 관리할 수 있습니다.
ms.openlocfilehash: 5d793bea8a22d9908551fff67c9d27afffdf1d86
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619824"
---
# <a name="set-up-a-connector-to-archive-webpage-data"></a><span data-ttu-id="8eb56-104">웹 페이지 데이터를 보관할 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="8eb56-104">Set up a connector to archive webpage data</span></span>

<span data-ttu-id="8eb56-105">Microsoft 365 규정 준수 센터의 Globanet 커넥터를 사용하여 웹 페이지의 데이터를 Microsoft 365 조직의 사용자 사서함으로 가져오고 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-105">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from webpages to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="8eb56-106">Globanet은 특정 웹 사이트 또는 전체 도메인에서 특정 웹 페이지(및 해당 페이지의 모든 링크)를 캡처하는 [웹](https://globanet.com/webpage-capture) 페이지 캡처 커넥터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-106">Globanet provides a [Webpage Capture](https://globanet.com/webpage-capture) connector that captures specific webpages (and any links on those pages) in a specific website or an entire domain.</span></span> <span data-ttu-id="8eb56-107">커넥터는 웹 페이지 콘텐츠를 PDF, PNG 또는 사용자 지정 파일 형식으로 변환한 다음 변환된 파일을 전자 메일 메시지에 첨부한 다음 해당 전자 메일 항목을 Microsoft 365의 사용자 사서함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-107">The connector converts the webpage content to a PDF, PNG, or custom file format and then attaches the converted files to an email message and then imports those email items to user mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="8eb56-108">웹 페이지 콘텐츠가 사용자 사서함에 저장되고 나면 소송 보존, eDiscovery, 보존 정책 및 보존 레이블과 같은 Microsoft 365 규정 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-108">After webpage content is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, and retention policies and retention labels.</span></span> <span data-ttu-id="8eb56-109">웹 페이지 캡처 커넥터를 사용하여 Microsoft 365에서 데이터를 가져오고 보관하면 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-109">Using a Webpage Capture connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-webpage-data"></a><span data-ttu-id="8eb56-110">보관 웹 페이지 데이터 개요</span><span class="sxs-lookup"><span data-stu-id="8eb56-110">Overview of archiving webpage data</span></span>

<span data-ttu-id="8eb56-111">다음 개요에서는 커넥터를 사용하여 Microsoft 365에서 웹 페이지 콘텐츠를 보관하는 프로세스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-111">The following overview explains the process of using a connector to archive webpage content in Microsoft 365.</span></span>

![웹 페이지 데이터에 대한 보관 워크플로](../media/WebPageCaptureConnectorWorkflow.png)

1. <span data-ttu-id="8eb56-113">조직은 웹 페이지 원본과 함께 웹 페이지 캡처 사이트를 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-113">Your organization works with the webpage source to set up and configure a Webpage Capture site.</span></span>

2. <span data-ttu-id="8eb56-114">24시간마다 웹 페이지 원본 항목이 Globanet Merge1 사이트에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-114">Once every 24 hours, the webpage sources items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="8eb56-115">또한 커넥터는 웹 페이지 콘텐츠를 변환하고 전자 메일 메시지에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-115">The connector also converts and attaches the content of a webpage to an email message.</span></span>

3. <span data-ttu-id="8eb56-116">Microsoft 365 규정 준수 센터에서 만든 웹 페이지 캡처 커넥터는 매일 Globanet Merge1 사이트에 연결하고 웹 페이지 항목을 Microsoft 클라우드의 보안 Azure Storage 위치로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-116">The Webpage Capture connector that you create in the Microsoft 365 compliance center, connects to the Globanet Merge1 site every day and transfers the webpage items to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="8eb56-117">커넥터는 3단계에 설명된 자동 사용자 매핑의 *Email* 속성 값을 사용하여 변환된 웹 페이지 항목을 특정 사용자의 사서함으로 [가져올 수 있습니다.](#step-3-map-users-and-complete-the-connector-setup)</span><span class="sxs-lookup"><span data-stu-id="8eb56-117">The connector imports the converted webpage items to the mailboxes of specific users by using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="8eb56-118">받은 편지함 **폴더의 Webpage Capture라는** 하위 폴더가 사용자 사서함에 만들어지며 웹 페이지 항목을 해당 폴더로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-118">A subfolder in the Inbox folder named **Webpage Capture** is created in the user mailboxes, and the webpage items are imported to that folder.</span></span> <span data-ttu-id="8eb56-119">커넥터는 Email 속성 값을 사용하여 이 *기능을* 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-119">The connector does this by using the value of the *Email* property.</span></span> <span data-ttu-id="8eb56-120">모든 웹 페이지 항목에는 [2단계에서](#step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site)웹 페이지 캡처 커넥터를 구성할 때 제공된 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-120">Every webpage item contains this property, which is populated with the email addresses provided when you configure the Webpage Capture connector in [Step 2](#step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8eb56-121">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="8eb56-121">Before you begin</span></span>

- <span data-ttu-id="8eb56-122">Microsoft 커넥터에 대한 Globanet Merge1 계정을 만드시다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-122">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="8eb56-123">이 계정을 만들하려면 [Globanet 고객 지원에 문의하세요.](https://globanet.com/ms-connectors-contact/)</span><span class="sxs-lookup"><span data-stu-id="8eb56-123">To create this account, contact [Globanet Customer Support](https://globanet.com/ms-connectors-contact/).</span></span> <span data-ttu-id="8eb56-124">1단계에서 커넥터를 만들 때 이 계정에 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-124">You will sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="8eb56-125">웹 페이지 항목을 변환할 사용자 지정 파일 형식을 설정하려면 Globanet 지원과 함께 작업해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-125">You need to work with Globanet support to set up a custom file format to convert the webpage items to.</span></span> <span data-ttu-id="8eb56-126">자세한 내용은 Merge1 Third-Party Connectors 사용자 가이드를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8eb56-126">For more information, see the Merge1 Third-Party Connectors User Guide in</span></span> 

- <span data-ttu-id="8eb56-127">1단계에서 Webpage Capture 커넥터를 만들고 3단계에서 완료하는 사용자는 Exchange Online의 사서함 가져오기 내보내기 역할에 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-127">The user who creates the Webpage Capture connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="8eb56-128">이 역할은 Microsoft 365 규정 준수 센터의 데이터 커넥터 페이지에서 커넥터를 추가하는 데 필요합니다. </span><span class="sxs-lookup"><span data-stu-id="8eb56-128">This role is required to add connectors on the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="8eb56-129">기본적으로 이 역할은 Exchange Online의 역할 그룹에 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-129">By default, this role is not assigned to a role group in Exchange Online.</span></span> <span data-ttu-id="8eb56-130">Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-130">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="8eb56-131">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-131">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="8eb56-132">자세한 내용은 "Exchange [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Online에서 [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서에서 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8eb56-132">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-webpage-capture-connector"></a><span data-ttu-id="8eb56-133">1단계: 웹 페이지 캡처 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="8eb56-133">Step 1: Set up the Webpage Capture connector</span></span>

<span data-ttu-id="8eb56-134">첫 번째 단계는 데이터  커넥터에 액세스하고 웹 페이지 원본 데이터에 대한 커넥터를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-134">The first step is to access to the **Data Connectors** and create a connector for Web Page source data.</span></span>

1. <span data-ttu-id="8eb56-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click Data **connectors**  >  **Webpage Capture.**</span><span class="sxs-lookup"><span data-stu-id="8eb56-135">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **Webpage Capture**.</span></span>

2. <span data-ttu-id="8eb56-136">웹 페이지 **캡처 제품** 설명 페이지에서 커넥터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8eb56-136">On the **Webpage Capture** product description page, click **Add connector**.</span></span>

3. <span data-ttu-id="8eb56-137">서비스 약관 **페이지에서** 수락을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8eb56-137">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="8eb56-138">커넥터를 식별하는 고유한 이름을 입력하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="8eb56-138">Enter a unique name that identifies the connector, and then click **Next**.</span></span>

5. <span data-ttu-id="8eb56-139">Merge1 계정에 로그인하여 커넥터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-139">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="8eb56-140">2단계: Globanet Merge1 사이트에서 웹 페이지 캡처 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="8eb56-140">Step 2: Configure the Webpage Capture connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="8eb56-141">두 번째 단계는 Globanet Merge1 사이트에서 웹 페이지 캡처 커넥터를 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-141">The second step is to configure the Webpage Capture connector on the Globanet Merge1 site.</span></span> <span data-ttu-id="8eb56-142">웹 페이지 캡처 커넥터를 구성하는 방법에 대한 자세한 내용은 [Merge1 Third-Party Connectors 사용자 가이드를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="8eb56-142">For information about how to configure the Webpage Capture connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="8eb56-143">저장 **&** 마친 후 Microsoft  365 준수 센터의 커넥터 마법사에 있는 사용자 매핑 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-143">After you click **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="8eb56-144">3단계: 사용자 매핑 및 커넥터 설정 완료</span><span class="sxs-lookup"><span data-stu-id="8eb56-144">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="8eb56-145">사용자를 매핑하고 Microsoft 365 규정 준수 센터에서 커넥터 설정을 완료하려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="8eb56-145">To map users and complete the connector setup in the Microsoft 365 compliance center, follow the steps below:</span></span>

1. <span data-ttu-id="8eb56-146">Microsoft **365** 사용자에 대한 사용자 매핑 웹 페이지 캡처 페이지에서 자동 사용자 매핑을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-146">On the **Map Webpage Capture users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="8eb56-147">웹 페이지 캡처 항목에는 조직의 사용자에 대한 전자 메일 주소가 포함된 *Email이라는* 속성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-147">The Webpage Capture items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="8eb56-148">커넥터가 이 주소를 Microsoft 365 사용자와 연결하면 항목이 해당 사용자의 사서함으로 가져오기됩니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-148">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user's mailbox.</span></span>

2. <span data-ttu-id="8eb56-149">다음을 **클릭하고** 설정을 검토하고  데이터 커넥터 페이지로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-149">Click **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-webpage-capture-connector"></a><span data-ttu-id="8eb56-150">4단계: 웹 페이지 캡처 커넥터 모니터링</span><span class="sxs-lookup"><span data-stu-id="8eb56-150">Step 4: Monitor the Webpage Capture connector</span></span>

<span data-ttu-id="8eb56-151">웹 페이지 캡처 커넥터를 만든 후 Microsoft 365 준수 센터에서 커넥터 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-151">After you create the Webpage Capture connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="8eb56-152">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span><span class="sxs-lookup"><span data-stu-id="8eb56-152">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="8eb56-153">커넥터 **탭을** 클릭한 다음 **웹 페이지** 캡처 커넥터를 선택하여 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-153">Click the **Connectors** tab and then select the **Webpage Capture** connector to display the flyout page.</span></span> <span data-ttu-id="8eb56-154">이 페이지에는 커넥터에 대한 속성과 정보가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-154">This page contains the properties and information about the connector.</span></span>

3. <span data-ttu-id="8eb56-155">원본이 **있는 커넥터** 상태  아래에서 다운로드 로그 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-155">Under **Connector status with source**, click the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="8eb56-156">이 로그에는 Microsoft 클라우드로 가져온 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-156">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="8eb56-157">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="8eb56-157">Known issues</span></span>

- <span data-ttu-id="8eb56-158">현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-158">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="8eb56-159">더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8eb56-159">Support for larger items will be available at a later date.</span></span>
