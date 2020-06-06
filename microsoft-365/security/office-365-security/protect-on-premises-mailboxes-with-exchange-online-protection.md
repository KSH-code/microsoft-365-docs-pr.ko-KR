---
title: 독립형 EOP를 사용하여 중국에 있는 온-프레미스 사서함 보호
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 중국의 관리자 21Vianet에서 운영 하는 Office 365을 사용 하 여 온-프레미스 사서함을 보호 하기 위해 독립 실행형 EOP (Exchange Online Protection)를 사용 하는 방법을 확인할 수 있습니다.
ms.openlocfilehash: 3e9ba8400ce9c545dd26f2dadce70595f5c5695e
ms.sourcegitcommit: 2de6e07ec55d78a5c5cf2f45732ae68acf058bcf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2020
ms.locfileid: "44587983"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a><span data-ttu-id="2a737-103">독립형 EOP를 사용하여 중국에 있는 온-프레미스 사서함 보호</span><span class="sxs-lookup"><span data-stu-id="2a737-103">Protect on-premises mailboxes in China with standalone EOP</span></span>

> [!NOTE]
> <span data-ttu-id="2a737-104">이 문서는 중국의 21Vianet에서 운영 하는 Office 365에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-104">This article applies only to Office 365 operated by 21Vianet in China.</span></span>

<span data-ttu-id="2a737-105">온-프레미스에서 사서함의 일부 또는 전체를 호스트 하는 경우에도 EOP (Exchange Online Protection)를 사용 하 여 사서함을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-105">Even if you plan to host some or all of your mailboxes on-premises, you can still protect the mailboxes with Exchange Online Protection (EOP).</span></span> <span data-ttu-id="2a737-106">커넥터를 구성 하려면 계정이 전역 관리자 또는 Exchange 회사 관리자 (조직 관리 역할 그룹) 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-106">To configure connectors, your account must be a global admin, or an Exchange Company Administrator (the Organization Management role group).</span></span> <span data-ttu-id="2a737-107">Office 365 권한이 Exchange 권한과 관련 된 방식에 대 한 자세한 내용은 [21vianet에서 운영 하는 office 365에서 관리자 역할 할당](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-21vianet)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2a737-107">For information about how Office 365 permissions relate to Exchange permissions, see [Assigning admin roles in Office 365 operated by 21Vianet](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles?view=o365-21vianet).</span></span> <span data-ttu-id="2a737-108">모든 Exchange 사서함이 온-프레미스에 있는 경우 다음 단계를 수행 하 여 EOP 서비스를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-108">If all of your Exchange mailboxes are on-premise, follow these steps to set up your EOP service.</span></span>

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a><span data-ttu-id="2a737-109">1 단계: Microsoft 365 관리 센터를 사용 하 여 도메인 추가 및 확인</span><span class="sxs-lookup"><span data-stu-id="2a737-109">Step 1: Use the Microsoft 365 admin center to add and verify your domain</span></span>

1. <span data-ttu-id="2a737-110">Microsoft 365 관리 센터에서 설정으로 이동 하 여 서비스에 도메인을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-110">In the Microsoft 365 admin center, navigate to Setup to add your domain to the service.</span></span>

2. <span data-ttu-id="2a737-111">도메인 소유권을 확인 하기 위해 포털의 단계에 따라 DNS 호스팅 공급자에 게 해당 DNS 레코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-111">Follow the steps in the portal to add the applicable DNS records to your DNS-hosting provider in order to verify domain ownership.</span></span>

> [!TIP]
> <span data-ttu-id="2a737-112">도메인 [및 사용자를 21vianet에서 운영 하는 office 365에 추가](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain?view=o365-21vianet) 하 고, [dns 레코드를 관리할 때 office 365에 대 한 Dns 레코드를 만들려면](https://docs.microsoft.com/microsoft-365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?view=o365-21vianet) 도메인을 서비스에 추가 하 고 dns를 구성할 때 참조 하면 도움이 되는 리소스입니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-112">[Add your domain and users to Office 365 operated by 21Vianet](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain?view=o365-21vianet) and [Create DNS records for Office 365 when you manage your DNS records](https://docs.microsoft.com/microsoft-365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?view=o365-21vianet) are helpful resources to reference as you add your domain to the service and configure DNS.</span></span>

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a><span data-ttu-id="2a737-113">2 단계: 받는 사람 추가 및 도메인 유형 구성</span><span class="sxs-lookup"><span data-stu-id="2a737-113">Step 2: Add recipients and configure the domain type</span></span>

<span data-ttu-id="2a737-114">메일이 EOP 서비스를 통해 전달되도록 구성하려는 경우 먼저 받는 사람을 서비스에 추가하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-114">Before configuring your mail to flow to and from the EOP service, we recommend adding your recipients to the service.</span></span> <span data-ttu-id="2a737-115">[EOP에서 메일 사용자 관리](manage-mail-users-in-eop.md)에 설명된 것처럼 이러한 방법에는 몇 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-115">There are several ways in which you can do this, as documented in [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="2a737-116">또한 받는 사람을 추가한 후에 서비스 내에서 받는 사람 확인을 적용하기 위해 DBEB(디렉터리 기반 Edge 차단)를 사용 가능하게 설정하려면 도메인 유형을 신뢰할 수 있음으로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-116">Also, if you want to enable Directory Based Edge Blocking (DBEB) in order to enforce recipient verification within the service after adding your recipients, you need to set your domain type to Authoritative.</span></span> <span data-ttu-id="2a737-117">DBEB에 대 한 자세한 내용은 [디렉터리 기반 Edge 차단을 사용 하 여 잘못 된 받는 사람에 게 보낸 메시지 거부](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2a737-117">For more information about DBEB, see [Use Directory Based Edge Blocking to reject messages sent to invalid recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking).</span></span>

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a><span data-ttu-id="2a737-118">3단계: EAC를 사용하여 메일 흐름 설정</span><span class="sxs-lookup"><span data-stu-id="2a737-118">Step 3: Use the EAC to set up mail flow</span></span>

<span data-ttu-id="2a737-119">EOP 및 온-프레미스 메일 서버 간의 메일 흐름을 가능하게 하는 커넥터를 EAC(Exchange 관리 센터)에서 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-119">Create connectors in the Exchange admin center (EAC) that enable mail flow between EOP and your on-premises mail servers.</span></span> <span data-ttu-id="2a737-120">자세한 내용은 [Office 365에서 커넥터를 사용 하 여 메일 흐름 구성을](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2a737-120">For detailed instructions, see [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span>

 <span data-ttu-id="2a737-121">이 작업의 작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="2a737-121">How do you know this task worked?</span></span>

 <span data-ttu-id="2a737-122">[Office 365 커넥터를 확인 하 여 메일 흐름 테스트](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2a737-122">See [Test mail flow by validating your Office 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).</span></span>

## <a name="step-4-allow-inbound-port-25-smtp-access"></a><span data-ttu-id="2a737-123">4단계: 인바운드 포트 25 SMTP 액세스 허용</span><span class="sxs-lookup"><span data-stu-id="2a737-123">Step 4: Allow inbound port 25 SMTP access</span></span>

<span data-ttu-id="2a737-124">커넥터를 구성한 후에 DNS 레코드 업데이트가 전파될 수 있게 72시간 동안 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-124">After you configured connectors, wait 72 hours to allow propagation of your DNS-record updates.</span></span> <span data-ttu-id="2a737-125">이렇게 하면 방화벽 또는 메일 서버에서 인바운드 포트 25 SMTP 트래픽을 제한 하 여 EOP 데이터 센터 로부터의 메일 (특히 [url 및 Office 365에 대 한 ip 주소 범위](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)에 나열 된 ip 주소에서)을 허용 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-125">Following this, restrict inbound port-25 SMTP traffic on your firewall or mail servers to accept mail only from the EOP datacenters, specifically from the IP addresses listed at [URLs and IP address ranges for Office 365](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).</span></span> <span data-ttu-id="2a737-126">이렇게 하면 수신 가능한 인바운드 메시지 범위를 제한하여 온-프레미스 환경을 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-126">This protects your on-premises environment by limiting the scope of inbound messages you can receive.</span></span> <span data-ttu-id="2a737-127">또한 메일 릴레이를 위한 연결이 허용된 IP 주소를 제어하는 설정이 메일 서버에 있는 경우에는 해당 설정도 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-127">Additionally, if you have settings on your mail server that control the IP addresses allowed to connect for mail relay, update those settings as well.</span></span>

> [!TIP]
> <span data-ttu-id="2a737-p105">연결 제한 시간을 60초로 지정하여 SMTP 서버의 설정을 구성합니다. 이 설정은 대부분의 상황에 적합하며 대용량 첨부 파일 포함된 메시지를 보내는 등의 경우 어느 정도의 지연이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-p105">Configure settings on the SMTP server with a connection time out of 60 seconds. This setting is acceptable for most situations, allowing for some delay in the case of a message sent with a large attachment, for instance.</span></span>

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a><span data-ttu-id="2a737-130">5 단계: 스팸이 각 사용자의 정크 메일 폴더로 라우팅되도록 확인</span><span class="sxs-lookup"><span data-stu-id="2a737-130">Step 5: Ensure that spam is routed to each user's Junk Email folder</span></span>

<span data-ttu-id="2a737-131">스팸(정크) 메일이 각 사용자의 정크 메일 폴더로 라우팅되도록 하려면 몇 가지 구성 단계를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-131">To ensure that spam (junk) email is routed correctly to each user's Junk Email folder, you must perform a couple of configuration steps.</span></span> <span data-ttu-id="2a737-132">[하이브리드 환경의 정크 메일 폴더에 스팸을 배달 하도록 독립 실행형 EOP 구성](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)에 단계가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-132">The steps are provided in [Configure standalone EOP to deliver spam to the Junk Email folder in hybrid environments](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md).</span></span> <span data-ttu-id="2a737-133">각 사용자의 정크 메일 폴더로 메시지를 이동 하지 않으려면 스팸 방지 정책 (콘텐츠 필터 정책이 라고도 함)을 편집 하 여 다른 작업을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-133">If you don't want to move messages to each user's Junk Email folder, you may choose another action by editing your anti-spam policies (also known as content filter policies).</span></span> <span data-ttu-id="2a737-134">자세한 내용은 [Office 365의 스팸 방지 정책 구성하기](configure-your-spam-filter-policies.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2a737-134">For more information, see [Configure anti-spam policies in Office 365](configure-your-spam-filter-policies.md).</span></span>

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a><span data-ttu-id="2a737-135">6 단계: Microsoft 365 관리 센터를 사용 하 여 MX 레코드가 EOP를 가리키도록 지정</span><span class="sxs-lookup"><span data-stu-id="2a737-135">Step 6: Use the Microsoft 365 admin center to point your MX record to EOP</span></span>

<span data-ttu-id="2a737-136">Office 365 도메인 구성 단계에 따라 도메인의 MX 레코드를 업데이트하여 인바운드 전자 메일이 EOP를 통해 이동하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-136">Follow the Office 365 domain configuration steps to update your MX record for your domain, so that your inbound email flows through EOP.</span></span> <span data-ttu-id="2a737-137">자세한 내용은 [dns 레코드를 관리할 때 Office 365에 대 한 dns 레코드 만들기](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)를 다시 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2a737-137">For more information, you can again reference [Create DNS records for Office 365 when you manage your DNS records](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

<span data-ttu-id="2a737-138">이 작업의 작동 여부는 어떻게 확인하나요?</span><span class="sxs-lookup"><span data-stu-id="2a737-138">How do you know this task worked?</span></span>

 <span data-ttu-id="2a737-139">[Office 365 커넥터를 확인 하 여 메일 흐름 테스트](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2a737-139">See [Test mail flow by validating your Office 365 connectors](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow).</span></span>

<span data-ttu-id="2a737-p108">이 시점은 제대로 구성된 아웃바운드 온-프레미스 커넥터에 대한 서비스 배달을 확인했으며 MX 레코드가 EOP를 가리키고 있는지 확인한 상태입니다. 이제 다음 추가 테스트를 실행하도록 선택하여 서비스에서 온-프레미스 환경으로 이메일이 전달되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-p108">At this point, you've verified service delivery for a properly configured Outbound on-premises connector, and you've verified that your MX record is pointing to EOP. You can now choose to run the following additional tests to verify that an email will be successfully delivered by the service to your on-premises environment:</span></span>

- <span data-ttu-id="2a737-142">원격 연결 분석기에서 **Office 365** 탭을 클릭한 다음 **인터넷 전자 메일 테스트** 아래에 있는 **인바운드 SMTP 전자 메일** 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-142">In the Remote Connectivity Analyzer, click the **Office 365** tab, and then run the **Inbound SMTP Email** test located under **Internet Email Tests**.</span></span>

- <span data-ttu-id="2a737-p109">도메인이 서비스에 추가한 도메인과 일치하는 조직의 메일 받는 사람에게 웹 기반 전자 메일 계정에서 전자 메일 메시지를 보냅니다. Microsoft Outlook 또는 다른 전자 메일 클라이언트를 사용하여 온-프레미스 사서함으로의 메시지 배달을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-p109">Send an email message from any web-based email account to a mail recipient in your organization whose domain matches the domain you added to the service. Confirm delivery of the message to the on-premises mailbox using Microsoft Outlook or another email client.</span></span>

- <span data-ttu-id="2a737-145">아웃바운드 전자 메일 테스트를 실행하려면 조직 사용자가 웹 기반 전자 메일 계정에 전자 메일을 보내도록 한 다음 메시지 수신을 확인하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-145">If you want to run an outbound email test, you can send an email message from a user in your organization to a web-based email account and confirm that the message is received.</span></span>

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a><span data-ttu-id="2a737-146">덜 일반적인 경우: 온-프레미스 및 클라우드에서 사서함이 포함 된 하이브리드 설정</span><span class="sxs-lookup"><span data-stu-id="2a737-146">Less common: A hybrid setup with mailboxes on-premises and in the cloud</span></span>

<span data-ttu-id="2a737-147">Exchange Online에서 Exchange 사서함 온-프레미스와 클라우드에서 하나 이상의 사서함을 사용 하는 경우 *하이브리드* 설치가 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-147">If you have Exchange mailboxes on-premises and one or more mailboxes in the cloud in Exchange Online, you have a *hybrid* setup.</span></span> <span data-ttu-id="2a737-148">하이브리드 설정에서 약속 있음/없음 일정 공유 및 메일 라우팅과 같은 기능은 온-프레미스 및 클라우드 환경에서 함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-148">In a hybrid setup, features such as free/busy calendar sharing and mail routing work together in your on-premises and cloud environments.</span></span> <span data-ttu-id="2a737-149">사서함을 Exchange Online으로 전환 하는 동안 하이브리드 설치가 진행 되 고 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-149">You might have a hybrid setup in place while you transition mailboxes to Exchange Online.</span></span> <span data-ttu-id="2a737-150">하이브리드 환경은 EOP 독립 실행형 보호와는 다른 방식으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-150">A hybrid environment is set up differently than EOP standalone protection.</span></span>

<span data-ttu-id="2a737-151">대부분의 직원에 대해 클라우드 기반 전자 메일을 활용 하려면 하이브리드 시나리오를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-151">You might choose a hybrid scenario to take advantage of cloud-based email for most of your employees.</span></span> <span data-ttu-id="2a737-152">이 작업은 온-프레미스의 일부 사서함을 호스트 하는 동안에도 가능 합니다. 예를 들어 법률 부서에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-152">You can do this while also hosting some mailboxes on-premises; for example, for your legal department.</span></span>

<span data-ttu-id="2a737-153">하이브리드 설치는 복잡할 수 있지만 다양 한 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a737-153">A hybrid setup can be complex, but it has many benefits.</span></span> <span data-ttu-id="2a737-154">Exchange를 사용 하 여 하이브리드 시나리오를 설정 하는 방법에 대 한 자세한 내용은 [Exchange Server 하이브리드 배포](https://docs.microsoft.com/Exchange/exchange-hybrid)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2a737-154">To learn more about setting up hybrid scenarios with Exchange, see [Exchange Server hybrid deployments](https://docs.microsoft.com/Exchange/exchange-hybrid).</span></span>
