---
title: Microsoft 365에서 Red tail Speak 데이터를 보관할 커넥터 설정
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
description: 관리자는 Globanet에서 Microsoft 365로 Red tail Speak 데이터를 가져오고 보관하는 커넥터를 설정할 수 있습니다. 이 커넥터를 사용하면 Microsoft 365에서 타사 데이터 원본의 데이터를 보관할 수 있습니다. 이 데이터를 보관한 후 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 준수 기능을 사용하여 타사 데이터를 관리할 수 있습니다.
ms.openlocfilehash: ff66f00348bd3e73bdbd607bd4bd0c0f922786cc
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769213"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data"></a><span data-ttu-id="9b131-105">Redtail Speak 데이터를 보관할 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="9b131-105">Set up a connector to archive Redtail Speak data</span></span>

<span data-ttu-id="9b131-106">Microsoft 365 규정 준수 센터의 Globanet 커넥터를 사용하여 Redtail Speak에서 Microsoft 365 조직의 사용자 사서함으로 데이터를 가져오고 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-106">Use a Globanet connector in the Microsoft 365 compliance center to import and archive data from the Redtail Speak to user mailboxes in your Microsoft 365 organization.</span></span> <span data-ttu-id="9b131-107">Globanet은 [Redtail에서](https://globanet.com/redtail/) 항목을 수신하는 조직의 SFTP 서버에서 항목을 캡처하도록 구성된 Redtail Speak 커넥터를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-107">Globanet provides you with a [Redtail Speak](https://globanet.com/redtail/) connector that's configured to capture items from your organization’s SFTP server where the items are received from Redtail.</span></span> <span data-ttu-id="9b131-108">커넥터는 Redtail Speak의 콘텐츠를 전자 메일 메시지 형식으로 변환한 다음 해당 항목을 Microsoft 365의 사용자 사서함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-108">The connector converts the content from Redtail Speak to an email message format and then imports those items to the user's mailbox in Microsoft 365.</span></span>

<span data-ttu-id="9b131-109">Redtail Speak 데이터가 사용자 사서함에 저장되고 나면 소송 보존, eDiscovery, 보존 정책 및 보존 레이블과 같은 Microsoft 365 규정 준수 기능을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-109">After Redtail Speak data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, retention policies, and retention labels.</span></span> <span data-ttu-id="9b131-110">Redtail Speak 커넥터를 사용하여 Microsoft 365에서 데이터를 가져오고 보관하면 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-110">Using a Redtail Speak connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-the-redtail-speak-data"></a><span data-ttu-id="9b131-111">Redtail Speak 데이터 보관 개요</span><span class="sxs-lookup"><span data-stu-id="9b131-111">Overview of archiving the Redtail Speak data</span></span>

<span data-ttu-id="9b131-112">다음 개요에서는 커넥터를 사용하여 Microsoft 365에서 Redtail Speak 데이터를 보관하는 프로세스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-112">The following overview explains the process of using a connector to archive the Redtail Speak data in Microsoft 365.</span></span>

![Redtail Speak 데이터를 위한 보관 워크플로](../media/RedtailSpeakConnectorWorkflow.png)

1. <span data-ttu-id="9b131-114">조직은 Redtail Speak와 함께 Redtail Speak와 함께 매일 Redtail Speak에서 조직의 SFTP 서버로 메시지가 전달되는 SMTP 게이트웨이를 설정하고 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-114">Your organization works with Redtail Speak to set up and configure an SMTP gateway where messages are forwarded from Redtail Speak to your organization's SFTP server on a daily basis.</span></span>

2. <span data-ttu-id="9b131-115">24시간마다 Redtail Speak 항목이 Globanet Merge1 사이트에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-115">Once every 24 hours, the Redtail Speak items are copied to the Globanet Merge1 site.</span></span> <span data-ttu-id="9b131-116">또한 이 커넥터는 Redtail Speak 항목을 전자 메일 메시지 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-116">The connector also converts the Redtail Speak items to an email message format.</span></span>

3. <span data-ttu-id="9b131-117">Microsoft 365 규정 준수 센터에서 만든 Redtail Speak 커넥터는 매일 Globanet Merge1 사이트에 연결하고 메시지를 Microsoft 클라우드의 보안 Azure Storage 위치로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-117">The Redtail Speak connector that you create in the Microsoft 365 compliance center connects to the Globanet Merge1 site every day and transfers the messages to a secure Azure Storage location in the Microsoft cloud.</span></span>

4. <span data-ttu-id="9b131-118">커넥터는 3단계에 설명된 자동 사용자 매핑의 *Email* 속성 값을 사용하여 변환된 Redtail Speak 항목을 특정 사용자의 사서함으로 [가져올 수 있습니다.](#step-3-map-users-and-complete-the-connector-setup)</span><span class="sxs-lookup"><span data-stu-id="9b131-118">The connector imports the converted Redtail Speak items to the mailboxes of specific users using the value of the *Email* property of the automatic user mapping as described in [Step 3](#step-3-map-users-and-complete-the-connector-setup).</span></span> <span data-ttu-id="9b131-119">받은 편지함 폴더 **Redtail Speak라는** 받은 편지함 폴더의 하위 폴더가 사용자 사서함에 만들어지며 항목을 해당 폴더로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-119">A subfolder in the Inbox folder named **Redtail Speak** is created in the user mailboxes, and the items are imported to that folder.</span></span> <span data-ttu-id="9b131-120">커넥터는 Email 속성 값을 사용하여 항목을 가져올 사서함을 결정할 *수* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-120">The connector determines which mailbox to import items to by using the value of the *Email* property.</span></span> <span data-ttu-id="9b131-121">모든 Redtail Speak 항목에는 항목의 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-121">Every Redtail Speak item contains this property, which is populated with the email address of every participant of the item.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9b131-122">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="9b131-122">Before you begin</span></span>

- <span data-ttu-id="9b131-123">Microsoft 커넥터에 대한 Globanet Merge1 계정을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-123">Create a Globanet Merge1 account for Microsoft connectors.</span></span> <span data-ttu-id="9b131-124">계정을 만들 경우 [Globanet 고객](https://globanet.com/contact-us/)지원에 문의하세요.</span><span class="sxs-lookup"><span data-stu-id="9b131-124">To create an account, contact [Globanet Customer Support](https://globanet.com/contact-us/).</span></span> <span data-ttu-id="9b131-125">1단계에서 커넥터를 만들 때 이 계정에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-125">You need to sign into this account when you create the connector in Step 1.</span></span>

- <span data-ttu-id="9b131-126">2단계에서 조직의 SFTP 서버를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-126">In Step 2, you need to specify your organization's SFTP server.</span></span> <span data-ttu-id="9b131-127">이 단계는 Globanet Merge1이 SFTP를 통해 Redtail Speak 데이터를 수집하기 위해 연결될 수 있도록 하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-127">This step is necessary so that Globanet Merge1 can contact it to collect Redtail Speak data via SFTP.</span></span>

- <span data-ttu-id="9b131-128">1단계에서 Redtail Speak Importer 커넥터를 만들고 3단계에서 완료하는 사용자는 Exchange Online의 사서함 가져오기 내보내기 역할에 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-128">The user who creates the Redtail Speak Importer connector in Step 1 (and completes it in Step 3) must be assigned to the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="9b131-129">이 역할은 Microsoft 365 규정 준수 센터의 데이터 커넥터 페이지에서 커넥터를 추가하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-129">This role is required to add connectors on the Data connectors page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="9b131-130">이 역할은 기본적으로 Exchange Online의 역할 그룹에 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-130">This role is not assigned to any role group in Exchange Online by default.</span></span> <span data-ttu-id="9b131-131">Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-131">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="9b131-132">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-132">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="9b131-133">자세한 내용은 "Exchange [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Online에서 [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9b131-133">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="step-1-set-up-the-redtail-speak-connector"></a><span data-ttu-id="9b131-134">1단계: Redtail Speak 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="9b131-134">Step 1: Set up the Redtail Speak connector</span></span>

<span data-ttu-id="9b131-135">첫 번째 단계는 Microsoft  365 규정 준수 센터의 데이터 커넥터 페이지에 액세스하고 Redtail Speak 데이터에 대한 커넥터를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-135">The first step is to access to the **Data Connectors** page in the Microsoft 365 compliance center and create a connector for the Redtail Speak data.</span></span>

1. <span data-ttu-id="9b131-136">이동하여 데이터 커넥터 [https://compliance.microsoft.com](https://compliance.microsoft.com/)  &gt; **Redtail Speak를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b131-136">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and select **Data connectors** &gt; **Redtail Speak**.</span></span>

2. <span data-ttu-id="9b131-137">**Redtail Speak** 제품 설명 페이지에서 새 커넥터 **추가를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b131-137">On the **Redtail Speak** product description page, select **Add new connector**.</span></span>

3. <span data-ttu-id="9b131-138">서비스 약관 **페이지에서** 수락을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b131-138">On the **Terms of service** page, select **Accept**.</span></span>

4. <span data-ttu-id="9b131-139">커넥터를 식별하는 고유한 이름을 입력하고 다음을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="9b131-139">Enter a unique name that identifies the connector, and then select **Next**.</span></span>

5. <span data-ttu-id="9b131-140">Merge1 계정에 로그인하여 커넥터를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-140">Sign in to your Merge1 account to configure the connector.</span></span>

## <a name="step-2-configure-the-redtail-speak-connector-on-the-globanet-merge1-site"></a><span data-ttu-id="9b131-141">2단계: Globanet Merge1 사이트에서 Redtail Speak 커넥터 구성</span><span class="sxs-lookup"><span data-stu-id="9b131-141">Step 2: Configure the Redtail Speak connector on the Globanet Merge1 site</span></span>

<span data-ttu-id="9b131-142">두 번째 단계는 Merge1 사이트에서 Redtail Speak 커넥터를 구성하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-142">The second step is to configure the Redtail Speak connector on the Merge1 site.</span></span> <span data-ttu-id="9b131-143">Redtail Speak 커넥터를 구성하는 방법에 대한 자세한 내용은 [Merge1 Third-Party Connectors 사용자 가이드를 참조하십시오.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf)</span><span class="sxs-lookup"><span data-stu-id="9b131-143">For information about how to configure the Redtail Speak connector, see [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf).</span></span>

<span data-ttu-id="9b131-144">저장 & 완료를 선택하면 Microsoft  365 준수 센터의 커넥터 마법사에 있는 사용자 매핑 페이지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-144">After you select **Save & Finish**, the **User mapping** page in the connector wizard in the Microsoft 365 compliance center is displayed.</span></span>

## <a name="step-3-map-users-and-complete-the-connector-setup"></a><span data-ttu-id="9b131-145">3단계: 사용자 매핑 및 커넥터 설정 완료</span><span class="sxs-lookup"><span data-stu-id="9b131-145">Step 3: Map users and complete the connector setup</span></span>

<span data-ttu-id="9b131-146">사용자를 매핑하고 커넥터 설정을 완료하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-146">To map users and complete the connector setup, follow these steps:</span></span>

1. <span data-ttu-id="9b131-147">Redtail Speak 사용자 **지도 Microsoft 365** 사용자에 대해 말하기 페이지에서 자동 사용자 매핑을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-147">On the **Map Redtail Speak users to Microsoft 365 users** page, enable automatic user mapping.</span></span> <span data-ttu-id="9b131-148">Redtail Speak 항목에는 조직의 사용자에 대한 전자 메일 주소가 포함된 *Email이라는* 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-148">The Redtail Speak items include a property called *Email*, which contains email addresses for users in your organization.</span></span> <span data-ttu-id="9b131-149">커넥터가 이 주소를 Microsoft 365 사용자와 연결하면 항목이 해당 사용자의 사서함으로 가져오기됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-149">If the connector can associate this address with a Microsoft 365 user, the items are imported to that user’s mailbox.</span></span>

2. <span data-ttu-id="9b131-150">다음을 **선택하고** 설정을 검토하고 데이터  커넥터 페이지로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-150">Select **Next**, review your settings, and go to the **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="step-4-monitor-the-redtail-speak-connector"></a><span data-ttu-id="9b131-151">4단계: Redtail Speak 커넥터 모니터링</span><span class="sxs-lookup"><span data-stu-id="9b131-151">Step 4: Monitor the Redtail Speak connector</span></span>

<span data-ttu-id="9b131-152">Redtail Speak 커넥터를 만든 후 Microsoft 365 규정 준수 센터에서 커넥터 상태를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-152">After you create the Redtail Speak connector, you can view the connector status in the Microsoft 365 compliance center.</span></span>

1. <span data-ttu-id="9b131-153">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and select **Data connectors** in the left nav.</span><span class="sxs-lookup"><span data-stu-id="9b131-153">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and select **Data connectors** in the left nav.</span></span>

2. <span data-ttu-id="9b131-154">커넥터 **탭을** 선택한 다음 **Redtail Speak** 커넥터를 선택하여 플라이아웃 페이지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-154">Select the **Connectors** tab and then select the **Redtail Speak** connector to display the flyout page.</span></span> <span data-ttu-id="9b131-155">이 페이지에는 커넥터에 대한 속성과 정보가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-155">This page displays properties and information about the connector.</span></span>

3. <span data-ttu-id="9b131-156">원본이 **있는 커넥터** 상태  아래에서 다운로드 로그 링크를 선택하여 커넥터의 상태 로그를 열거나 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-156">Under **Connector status with source**, select the **Download log** link to open (or save) the status log for the connector.</span></span> <span data-ttu-id="9b131-157">이 로그에는 Microsoft 클라우드로 가져온 데이터가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-157">This log contains data that has been imported to the Microsoft cloud.</span></span>

## <a name="known-issues"></a><span data-ttu-id="9b131-158">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="9b131-158">Known issues</span></span>

- <span data-ttu-id="9b131-159">현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-159">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="9b131-160">더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b131-160">Support for larger items will be available at a later date.</span></span>
