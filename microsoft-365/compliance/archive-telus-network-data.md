---
title: Microsoft 365에서 TELUS 네트워크 데이터를 보관할 커넥터 설정
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
description: 관리자는 TeleMessage 커넥터를 설정하여 Microsoft 365의 TELUS 네트워크에서 SMS 데이터를 가져오고 보관할 수 있습니다. 이를 통해 Microsoft 365의 타사 데이터 원본에서 데이터를 보관할 수 있으므로 법적 보존, 콘텐츠 검색 및 보존 정책과 같은 규정 준수 기능을 사용하여 조직의 타사 데이터를 관리할 수 있습니다.
ms.openlocfilehash: 8df1d7d9787e118144cb9e0a55c66bdd1e766194
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620274"
---
# <a name="set-up-a-connector-to-archive-telus-network-data"></a><span data-ttu-id="6726c-104">TELUS 네트워크 데이터를 보관할 커넥터 설정</span><span class="sxs-lookup"><span data-stu-id="6726c-104">Set up a connector to archive TELUS Network data</span></span>

<span data-ttu-id="6726c-105">Microsoft 365 규정 준수 센터의 TeleMessage 커넥터를 사용하여 조직의 TELUS 네트워크에서 SMS(Short Messaging Service) 데이터를 가져오고 보관합니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-105">Use the TeleMessage connector in the Microsoft 365 compliance center to import and archive Short Messaging Service (SMS) data from your organization's TELUS Network.</span></span> <span data-ttu-id="6726c-106">커넥터를 설정하고 구성한 후 커넥터는 매일 한 번씩 조직의 TELUS 네트워크에 연결하고 Microsoft 365의 사서함으로 SMS 데이터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-106">After you set up and configure a connector, it connects to your organization's TELUS Network once every day, and imports SMS data to mailboxes in Microsoft 365.</span></span>

<span data-ttu-id="6726c-107">SMS 메시지를 사용자 사서함에 저장한 후 소송 보존, 콘텐츠 검색 및 Microsoft 365 보존 정책과 같은 Microsoft 365 규정 준수 기능을 TELUS 데이터에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-107">After SMS messages are stored in user mailboxes, you can apply Microsoft 365 compliance features such as Litigation Hold, Content Search, and Microsoft 365 retention policies to TELUS data.</span></span> <span data-ttu-id="6726c-108">예를 들어 콘텐츠 검색을 사용하여 TELUS SMS 메시지를 검색하거나 TELUS 데이터가 포함된 사서함을 고급 eDiscovery 사례의 보호자와 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-108">For example, you can search TELUS SMS messages using Content Search or associate the mailbox that contains the TELUS data with a custodian in an Advanced eDiscovery case.</span></span> <span data-ttu-id="6726c-109">TELUS 네트워크 커넥터를 사용하여 Microsoft 365에서 데이터를 가져오고 보관하면 조직이 정부 및 규제 정책을 준수하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-109">Using a TELUS Network connector to import and archive data in Microsoft 365 can help your organization stay compliant with government and regulatory policies.</span></span>

## <a name="overview-of-archiving-telus-network-data"></a><span data-ttu-id="6726c-110">TELUS 네트워크 데이터 보관 개요</span><span class="sxs-lookup"><span data-stu-id="6726c-110">Overview of archiving TELUS Network data</span></span>

<span data-ttu-id="6726c-111">다음 개요에서는 커넥터를 사용하여 Microsoft 365에서 TELUS 네트워크 데이터를 보관하는 프로세스에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-111">The following overview explains the process of using a connector to archive TELUS Network data in Microsoft 365.</span></span>

![TELUS 네트워크 보관 워크플로](../media/TelusNetworkConnectorWorkflow.png)

1. <span data-ttu-id="6726c-113">조직은 TeleMessage 및 TELUS와 함께 TELUS 네트워크 커넥터를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-113">Your organization works with TeleMessage and TELUS to set up a TELUS Network connector.</span></span> <span data-ttu-id="6726c-114">자세한 내용은 [TELUS Network Archiver를 참조하세요.](https://www.telemessage.com/office365-activation-for-telus-network-archiver/)</span><span class="sxs-lookup"><span data-stu-id="6726c-114">For more information, see [TELUS Network Archiver](https://www.telemessage.com/office365-activation-for-telus-network-archiver/).</span></span>

2. <span data-ttu-id="6726c-115">24시간마다 조직의 TELUS 네트워크의 SMS 메시지가 TeleMessage 사이트에 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-115">Once every 24 hours, SMS messages from your organization’s TELUS Network are copied to the TeleMessage site.</span></span>

3. <span data-ttu-id="6726c-116">Microsoft 365 규정 준수 센터에서 만든 TELUS 네트워크 커넥터는 매일 TeleMessage 사이트에 연결하고 이전 24시간의 SMS 메시지를 Microsoft 클라우드의 보안 Azure Storage 위치로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-116">The TELUS Network connector that you create in the Microsoft 365 compliance center connects to the TeleMessage site every day and transfers the SMS messages from the previous 24 hours to a secure Azure Storage location in the Microsoft Cloud.</span></span> <span data-ttu-id="6726c-117">또한 커넥터는 SMS 메시지의 내용을 전자 메일 메시지 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-117">The connector also converts the content of SMS messages to an email message format.</span></span>

4. <span data-ttu-id="6726c-118">커넥터는 모바일 통신 항목을 특정 사용자의 사서함으로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-118">The connector imports the mobile communication items to the mailbox of a specific user.</span></span> <span data-ttu-id="6726c-119">**TELUS SMS 네트워크 보관이라는** 새 폴더가 특정 사용자의 사서함에 만들어지며 항목을 해당 폴더로 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-119">A new folder named **TELUS SMS Network Archiver** is created in the specific user's mailbox and the items are imported to it.</span></span> <span data-ttu-id="6726c-120">커넥터는 사용자의 전자 메일 주소 속성 값을 사용하여 *매핑합니다.*</span><span class="sxs-lookup"><span data-stu-id="6726c-120">The connector does mapping by using the value of the *User’s Email address* property.</span></span> <span data-ttu-id="6726c-121">모든 SMS 메시지에는 SMS 메시지의 모든 참가자의 전자 메일 주소로 채워지는 이 속성이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-121">Every SMS message contains this property, which is populated with the email address of every participant of the SMS message.</span></span>

   <span data-ttu-id="6726c-122">사용자의 전자 메일 주소 속성 값을  사용한 자동 사용자 매핑 외에도 CSV 매핑 파일을 업로드하여 사용자 지정 매핑을 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-122">In addition to automatic user mapping using the value of the *User’s Email address* property, you can also implement custom mapping by uploading a CSV mapping file.</span></span> <span data-ttu-id="6726c-123">이 매핑 파일에는 조직의 사용자에 대한 휴대폰 번호와 해당 Microsoft 365 전자 메일 주소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-123">This mapping file contains the mobile phone number and corresponding Microsoft 365 email address for users in your organization.</span></span> <span data-ttu-id="6726c-124">자동 사용자 매핑과 사용자 지정 매핑을 모두 사용하도록 설정하면 모든 TELUS 항목에 대해 커넥터가 먼저 사용자 지정 매핑 파일을 관니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-124">If you enable both automatic user mapping and custom mapping, for every TELUS item the connector first looks at custom mapping file.</span></span> <span data-ttu-id="6726c-125">사용자의 휴대폰 번호에 해당하는 유효한 Microsoft 365 사용자를 찾을 수 없는 경우 커넥터는 가져오려고 하는 항목의 전자 메일 주소 속성 값을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-125">If it doesn't find a valid Microsoft 365 user that corresponds to a user's mobile phone number, the connector will use the values in the email address property of the item it's trying to import.</span></span> <span data-ttu-id="6726c-126">커넥터가 사용자 지정 매핑 파일 또는 TELUS 항목의 전자 메일 주소 속성에서 유효한 Microsoft 365 사용자를 찾지 못하면 항목을 가져오지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-126">If the connector doesn't find a valid Microsoft 365 user in either the custom mapping file or in the email address property of the TELUS item, the item won't be imported.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6726c-127">시작하기 전에</span><span class="sxs-lookup"><span data-stu-id="6726c-127">Before you begin</span></span>

<span data-ttu-id="6726c-128">TELUS 네트워크 데이터를 보관하는 데 필요한 구현 단계 중 일부는 Microsoft 365 외부에 있으며 준수 센터에서 커넥터를 만들기 전에 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-128">Some of the implementation steps required to archive TELUS Network data are external to Microsoft 365 and must be completed before you can create a connector in the compliance center.</span></span>

- <span data-ttu-id="6726c-129">[TeleMessage에서 TELUS 네트워크 보관](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) 서비스 순서를 정하고 조직에 대한 유효한 관리 계정을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-129">Order the [TELUS Network Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365) and get a valid administration account for your organization.</span></span> <span data-ttu-id="6726c-130">준수 센터에서 커넥터를 만들 때 이 계정에 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-130">You'll need to sign into this account when you create the connector in the compliance center.</span></span>

- <span data-ttu-id="6726c-131">TeleMessage 온보더링 양식을 작성하고 TELUS에서 메시지 보관 서비스를 주문할 수 있도록 TELUS 네트워크 계정 및 대금 청구 연락처 세부 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-131">Obtain your TELUS Network account and billing contact details so you can fill-out the TeleMessage onboarding forms and order the message archiving service from TELUS.</span></span>

- <span data-ttu-id="6726c-132">TeleMessage 계정에 TELUS SMS 네트워크 보관이 필요한 모든 사용자를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-132">Register all users that require TELUS SMS Network archiving in the TeleMessage account.</span></span> <span data-ttu-id="6726c-133">사용자를 등록할 때 Microsoft 365 계정에 사용되는 동일한 전자 메일 주소를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6726c-133">When registering users, be sure to use the same email address that's used for their Microsoft 365 account.</span></span>

- <span data-ttu-id="6726c-134">직원은TELUS 모바일 네트워크에 회사 소유의 회사 및 회사 소유 휴대폰이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-134">Your employees must have corporate-owned and corporate-liable mobile phones on theTELUS mobile network.</span></span> <span data-ttu-id="6726c-135">Microsoft 365의 보관 메시지는 직원 소유 또는 BYOD(Bring Your Own Devices) 장치에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-135">Archiving messages in Microsoft 365 isn't available for employee-owned or Bring Your Own Devices (BYOD) devices.</span></span>

- <span data-ttu-id="6726c-136">TELUS 네트워크 커넥터를 만드는 사용자에게 Exchange Online에서 사서함 가져오기 내보내기 역할이 할당되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-136">The user who creates a TELUS Network connector must be assigned the Mailbox Import Export role in Exchange Online.</span></span> <span data-ttu-id="6726c-137">이는 Microsoft 365 규정 준수 센터의 **데이터** 커넥터 페이지에서 커넥터를 추가하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-137">This is required to add connectors in the **Data connectors** page in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="6726c-138">기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-138">By default, this role isn't assigned to any role group in Exchange Online.</span></span> <span data-ttu-id="6726c-139">Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-139">You can add the Mailbox Import Export role to the Organization Management role group in Exchange Online.</span></span> <span data-ttu-id="6726c-140">또는 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-140">Or you can create a role group, assign the Mailbox Import Export role, and then add the appropriate users as members.</span></span> <span data-ttu-id="6726c-141">자세한 내용은 "Exchange [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Online에서 [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6726c-141">For more information, see the [Create role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) or [Modify role groups](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) sections in the article "Manage role groups in Exchange Online".</span></span>

## <a name="create-a-telus-network-connector"></a><span data-ttu-id="6726c-142">TELUS 네트워크 커넥터 만들기</span><span class="sxs-lookup"><span data-stu-id="6726c-142">Create a TELUS Network connector</span></span>

<span data-ttu-id="6726c-143">이전 섹션에 설명된 선행 작업을 완료한 후 Microsoft 365 규정 준수 센터에서 TELUS 네트워크 커넥터를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-143">After you've completed the prerequisites described in the previous section, you can create TELUS Network connector in the Microsoft 365 compliance center.</span></span> <span data-ttu-id="6726c-144">커넥터는 사용자가 제공한 정보를 사용하여 TeleMessage 사이트에 연결하고 SMS 메시지를 Microsoft 365의 해당 사용자 사서함 상자로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-144">The connector uses the information you provide to connect to the TeleMessage site and transfer SMS messages to the corresponding user mailbox boxes in Microsoft 365.</span></span>

1. <span data-ttu-id="6726c-145">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click Data **connectors**  >  **TELUS Network.**</span><span class="sxs-lookup"><span data-stu-id="6726c-145">Go to [https://compliance.microsoft.com](https://compliance.microsoft.com/) and then click **Data connectors** > **TELUS Network**.</span></span>

2. <span data-ttu-id="6726c-146">**TELUS 네트워크** 제품 설명 페이지에서 커넥터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6726c-146">On the **TELUS Network** product description page, click **Add connector**</span></span>

3. <span data-ttu-id="6726c-147">서비스 약관 **페이지에서** 수락을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6726c-147">On the **Terms of service** page, click **Accept**.</span></span>

4. <span data-ttu-id="6726c-148">**TeleMessage** 로그인 페이지의 3단계 아래에서 다음 상자에 필요한 정보를 입력하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6726c-148">On the **Login to TeleMessage** page, under Step 3, enter the required information in the following boxes and then click **Next**.</span></span>

   - <span data-ttu-id="6726c-149">**사용자 이름:** TeleMessage 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-149">**Username:** Your TeleMessage username.</span></span>

   - <span data-ttu-id="6726c-150">**암호:** TeleMessage 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-150">**Password:** Your TeleMessage password.</span></span>

5. <span data-ttu-id="6726c-151">커넥터를 만든 후 팝업 창을 닫고 다음 페이지로 이동하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-151">After the connector is created, you can close the pop-up window and go to the next page.</span></span>

6. <span data-ttu-id="6726c-152">사용자 매핑 **페이지에서** 자동 사용자 매핑을 사용하도록 설정하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6726c-152">On the **User mapping** page, enable automatic user mapping and click **Next**.</span></span> <span data-ttu-id="6726c-153">사용자 지정 매핑이 필요한 경우 CSV 파일을 업로드하고 다음을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="6726c-153">In case you need custom mapping upload a CSV file, and click **Next**.</span></span>

7. <span data-ttu-id="6726c-154">설정을 검토한 다음 **마친을** 클릭하여 커넥터를 만드시다.</span><span class="sxs-lookup"><span data-stu-id="6726c-154">Review your settings, and then click **Finish** to create the connector.</span></span>

8. <span data-ttu-id="6726c-155">데이터 커넥터 페이지의 커넥터  탭으로 이동하여 새 커넥터의 가져오기 프로세스 진행률을 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="6726c-155">Go to the Connectors tab in **Data connectors** page to see the progress of the import process for the new connector.</span></span>

## <a name="known-issues"></a><span data-ttu-id="6726c-156">알려진 문제</span><span class="sxs-lookup"><span data-stu-id="6726c-156">Known issues</span></span>

- <span data-ttu-id="6726c-157">현재는 10MB보다 큰 첨부 파일 또는 항목 가져오기는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-157">At this time, we don't support importing attachments or items that are larger than 10 MB.</span></span> <span data-ttu-id="6726c-158">더 큰 항목에 대한 지원은 나중에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6726c-158">Support for larger items will be available at a later date.</span></span>
