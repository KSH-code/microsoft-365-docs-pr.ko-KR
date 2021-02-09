---
title: EOP & 도메인 설정 이동
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 9d64867b-ebdb-4323-8e30-4560d76b4c97
ms.custom:
- seo-marvel-apr2020
description: 이 문서에서는 EOP(Microsoft Exchange Online Protection) 조직(테넌트)에서 다른 조직으로 도메인 및 설정을 이동하는 방법을 배우게 됩니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4cfb5c31728174f7f7307e9492abc03a62f8bf9a
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150763"
---
# <a name="move-domains-and-settings-from-one-eop-organization-to-another"></a><span data-ttu-id="ac746-103">EOP 조직 간에 도메인 및 설정 이동</span><span class="sxs-lookup"><span data-stu-id="ac746-103">Move domains and settings from one EOP organization to another</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ac746-104">**적용 대상**</span><span class="sxs-lookup"><span data-stu-id="ac746-104">**Applies to**</span></span>
-  [<span data-ttu-id="ac746-105">Exchange Online Protection 독립 실행형</span><span class="sxs-lookup"><span data-stu-id="ac746-105">Exchange Online Protection standalone</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)

<span data-ttu-id="ac746-p101">비즈니스 요구 사항 변경 시 하나의 Microsoft EOP(Exchange Online Protection) 조직(테넌트)을 두 조직으로 분할하거나, 두 조직을 하나로 병합하거나, 조직 간에 도메인 및 EOP 설정을 이동해야 할 수 있습니다. EOP 조직 간의 이동은 까다로운 작업일 수 있지만 몇 가지 기본적인 원격 Windows PowerShell 스크립트를 사용하고 약간만 준비하면 비교적 적은 유지 관리 기간에 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-p101">Changing business requirements can sometimes require splitting one Microsoft Exchange Online Protection (EOP) organization (tenant) into two separate organizations, merging two organizations into one, or moving your domains and EOP settings from one organization to another organization. Moving from one EOP organization to a second EOP organization can be challenging, but with a few basic remote Windows PowerShell scripts and a small amount of preparation, this can be achieved with a relatively small maintenance window.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="ac746-108">EOP 독립 실행형(Standard) 조직에서 다른 EOP Standard 또는 Exchange Enterprise CAL with Services(EOP Premium) 조직으로 또는 EOP Premium 조직에서 다른 EOP Premium 조직으로 설정을 안정적으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-108">Settings can be reliably moved only from an EOP standalone (Standard) organization to either another EOP Standard or an Exchange Enterprise CAL with Services (EOP Premium) organization, or from an EOP Premium organization to another EOP Premium organization.</span></span> <span data-ttu-id="ac746-109">일부 고급 기능은 EOP Standard 조직에서 지원되지 않는 경우 EOP Premium 조직에서 EOP Standard 조직으로의 이동이 성공하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-109">Because some premium features are not supported in EOP Standard organizations, moves from an EOP Premium organization to an EOP Standard organization might not be successful.</span></span>
>
> - <span data-ttu-id="ac746-p103">이러한 지침은 EOP 필터링 전용 조직에 적용됩니다. Exchange Online 조직 간의 이동에는 추가적인 고려 사항이 있습니다. Exchange Online 조직은 이러한 지침의 범위에서 벗어납니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-p103">These instructions are for EOP filtering-only organizations. There are additional considerations in moving from one Exchange Online organization to another Exchange Online organization. Exchange Online organizations are out of scope for these instructions.</span></span>

<span data-ttu-id="ac746-p104">다음 예제에서는 Contoso, Ltd.가 Contoso Suites와 병합되었습니다. 다음 그림에서는 원본 EOP 조직(contoso.onmicrosoft.com)에서 대상 EOP 조직(contososuites.onmicrosoft.com)으로 도메인, 메일 사용자 및 그룹, 설정을 이동하는 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-p104">In the following example, Contoso, Ltd. has merged with Contoso Suites. The following image shows the process of moving domains, mail users and groups, and settings from the source EOP organization (contoso.onmicrosoft.com) to the target EOP organization (contososuites.onmicrosoft.com):</span></span>

![EOP 도메인 및 설정 이동](../../media/EOP-Move-domains-and-settings.jpg)

<span data-ttu-id="ac746-p105">확인된 도메인이 두 조직에 동시에 존재할 수 없는 경우 조직 간에 도메인을 이동하는 데 문제가 있을 수 있습니다. 다음 단계에서는 이 과정을 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-p105">The challenge in moving domains from one organization to another is that a verified domain can't exist in two organizations at the same time. The following steps help you work through this.</span></span>

## <a name="step-1-collect-data-from-the-source-organization"></a><span data-ttu-id="ac746-118">1단계: 원본 조직에서 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="ac746-118">Step 1: Collect data from the source organization</span></span>

<span data-ttu-id="ac746-119">대상 조직에서 원본 조직을 다시 만들려면 원본 조직에 대한 다음 정보를 수집하고 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-119">In order to re-create the source organization in the target organization, make sure that you collect and store the following information about the source organization:</span></span>

- <span data-ttu-id="ac746-120">도메인</span><span class="sxs-lookup"><span data-stu-id="ac746-120">Domains</span></span>
- <span data-ttu-id="ac746-121">메일 사용자</span><span class="sxs-lookup"><span data-stu-id="ac746-121">Mail users</span></span>
- <span data-ttu-id="ac746-122">그룹</span><span class="sxs-lookup"><span data-stu-id="ac746-122">Groups</span></span>
- <span data-ttu-id="ac746-123">스팸 방지</span><span class="sxs-lookup"><span data-stu-id="ac746-123">Anti-spam</span></span>
  - <span data-ttu-id="ac746-124">스팸 방지 정책(콘텐츠 필터 정책)입니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-124">Anti-spam policies (also known as content filter policies)</span></span>
  - <span data-ttu-id="ac746-125">아웃바운드 스팸 필터 정책</span><span class="sxs-lookup"><span data-stu-id="ac746-125">Outbound spam filter policies</span></span>
  - <span data-ttu-id="ac746-126">연결 필터 정책</span><span class="sxs-lookup"><span data-stu-id="ac746-126">Connection filter policies</span></span>
- <span data-ttu-id="ac746-127">맬웨어 방지 정책</span><span class="sxs-lookup"><span data-stu-id="ac746-127">Anti-malware policies</span></span>
- <span data-ttu-id="ac746-128">커넥터</span><span class="sxs-lookup"><span data-stu-id="ac746-128">Connectors</span></span>
- <span data-ttu-id="ac746-129">메일 흐름 규칙(전송 규칙라고도 알려지기)</span><span class="sxs-lookup"><span data-stu-id="ac746-129">Mail flow rules (also known as transport rules)</span></span>

  > [!NOTE]
  > <span data-ttu-id="ac746-130">메일 흐름 규칙 컬렉션의 내보내기 및 가져오기에 대한 cmdlet 지원은 현재 EOP Premium 구독 계획에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-130">Cmdlet support for the export and import of the mail flow rule collection is currently only supported for EOP Premium subscription plans.</span></span>

<span data-ttu-id="ac746-131">모든 설정을 수집하는 가장 쉬운 방법은 PowerShell을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-131">The easiest way to collect all of your settings is to use PowerShell.</span></span> <span data-ttu-id="ac746-132">독립 실행형 EOP PowerShell에 연결하려면 [Exchange Online Protection PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac746-132">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

<span data-ttu-id="ac746-p107">다음으로, 모든 설정을 수집하고 대상 테넌트로 가져올 .xml 파일을 내보낼 수 있습니다. 일반적으로 다음 코드 샘플과 같이 각 설정에 대한 **Get** cmdlet의 출력을 **Export-Clixml** cmdlet에 파이프하여 .xml 파일에 설정을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-p107">Next, you can collect all your settings and export them to an .xml file to be imported into the target tenant. In general, you can pipe the output of the **Get** cmdlet for each setting to the **Export-Clixml** cmdlet to save the settings in .xml files, as shown in the following code sample.</span></span>

<span data-ttu-id="ac746-135">독립 실행형 EOP PowerShell에서 해당 디렉터리를 찾아서 변경할 수 있는 위치에 Export라는 디렉터리를 만드십시오.</span><span class="sxs-lookup"><span data-stu-id="ac746-135">In standalone EOP PowerShell, create a directory called Export in a location that's easy to find and change to that directory.</span></span> <span data-ttu-id="ac746-136">예:</span><span class="sxs-lookup"><span data-stu-id="ac746-136">For example:</span></span>

```PowerShell
mkdir C:\EOP\Export
```

```PowerShell
cd C:\EOP\Export
```

<span data-ttu-id="ac746-137">다음 스크립트를 사용하여 원본 조직에서 모든 메일 사용자, 그룹, 스팸 방지 설정, 맬웨어 방지 설정, 커넥터 및 메일 흐름 규칙을 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-137">The following script can be used to collect all the mail users, groups, anti-spam settings, anti-malware settings, connectors, and mail flow rules in the source organization.</span></span> <span data-ttu-id="ac746-138">메모장과 같은 텍스트 편집기에 다음 텍스트를 복사하여 붙여넣고 방금 만든 Export 디렉터리에서 Source_EOP_Settings.ps1 파일을 저장한 후 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-138">Copy and paste the following text into a text editor like Notepad, save the file as Source_EOP_Settings.ps1 in the Export directory you just created, and run the following command:</span></span>

```PowerShell
& "C:\EOP\Export\Source_EOP_Settings.ps1"
```

```PowerShell
#****************************************************************************
# Export Domains
#*****************************************************************************
Get-AcceptedDomain | Export-Clixml Domains.xml
#****************************************************************************
# Export mail users
#
#****************************************************************************
Get-Recipient -ResultSize unlimited -RecipientTypeDetails MailUser | Export-Clixml MailUsers.xml
#****************************************************************************
# Groups
#
# If you're using directory synchronization, you can skip this step and
# simply sync to the target
# tenant.
# First, you need to capture information about the distribution groups.
#****************************************************************************
Get-Recipient -ResultSize unlimited -RecipientTypeDetails MailUniversalDistributionGroup | Export-Clixml DistributionGroups.xml
Get-Recipient -ResultSize unlimited -RecipientTypeDetails MailUniversalSecurityGroup | Export-Clixml SecurityGroups.xml
#****************************************************************************
# And then we'll use that output to loop through each group and get the
# members.
#****************************************************************************
$DGs = Import-Clixml .\DistributionGroups.xml
ForEach ($dg in $DGs) {Get-DistributionGroupMember -Identity $dg.name | Export-Clixml $dg.ExternalDirectoryObjectId}
$SGs = Import-Clixml .\SecurityGroups.xml
ForEach ($sg in $SGs) {Get-DistributionGroupMember -Identity $sg.name | Export-Clixml $sg.ExternalDirectoryObjectId}
#*****************************************************************************
# Export dynamic distribution groups - EOP Premium Only
#
# If you're using directory synchronization, then you can skip this step and simply
# sync to the target tenant.
#*****************************************************************************
Get-DynamicDistributionGroup -ResultSize unlimited | Export-Clixml DynamicDistributionGroups.xml
#*****************************************************************************
# Export mail contacts - EOP Premium Only
#
# If you're using directory synchronization, then you can skip this step and simply
# sync to the target tenant.
#*****************************************************************************
Get-MailContact -ResultSize unlimited -RecipientTypeDetails MailContact | Export-Clixml MailContacts.xml
#****************************************************************************
# Anti-spam
#****************************************************************************
Get-HostedConnectionFilterPolicy | Export-Clixml HostedConnectionFilterPolicy.xml
Get-HostedContentFilterPolicy | Export-Clixml HostedContentFilterPolicy.xml
Get-HostedContentFilterRule | Export-Clixml HostedContentFilterRule.xml
Get-HostedOutboundSpamFilterPolicy | Export-Clixml HostedOutboundSpamFilterPolicy.xml
#****************************************************************************
# Anti-malware policies
#****************************************************************************
Get-MalwareFilterPolicy | Export-Clixml MalwareFilterPolicy.xml
Get-MalwareFilterRule | Export-Clixml MalwareFilterRule.xml
#****************************************************************************
# Connectors
#****************************************************************************
Get-InboundConnector | Export-Clixml InboundConnector.xml
Get-OutboundConnector | Export-Clixml OutboundConnector.xml
#****************************************************************************
# Exchange mail flow rules
#****************************************************************************
$file = Export-TransportRuleCollection
Set-Content -Path ".TransportRules.xml" -Value $file.FileData -Encoding Byte
```

<span data-ttu-id="ac746-p110">Export 디렉터리에서 다음 명령을 실행하여 대상 조직으로 .xml 파일을 업데이트합니다. contoso.onmicrosoft.com 및 contososuites.onmicrosoft.com을 원본 및 대상 조직 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-p110">Run the following commands from the Export directory to update the .xml files with the target organization. Replace contoso.onmicrosoft.com and contososuites.onmicrosoft.com with your source and target organization names.</span></span>

```PowerShell
$files = ls
ForEach ($file in $files) { (Get-Content $file.Name) | Foreach-Object {$_ -replace 'contoso.onmicrosoft.com', 'contososuites.onmicrosoft.com'} | Set-Content $file.Name}
```

## <a name="step-2-add-domains-to-the-target-organization"></a><span data-ttu-id="ac746-141">2단계: 대상 조직에 도메인 추가</span><span class="sxs-lookup"><span data-stu-id="ac746-141">Step 2: Add domains to the target organization</span></span>

<span data-ttu-id="ac746-p111">다음 스크립트를 사용하여 대상 조직에 도메인을 추가합니다. 메모장과 같은 텍스트 편집기에 텍스트를 복사하여 붙여넣고 스크립트를 C:\EOP\Export\Add_Domains.ps1로 저장한 후 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-p111">Add domains to the target organization by using the following script. Copy and paste the text into a text editor like Notepad, save the script as C:\EOP\Export\Add_Domains.ps1, and run the following command:</span></span>

```PowerShell
& "C:\EOP\Export\Add_Domains.ps1"
```

<span data-ttu-id="ac746-144">이러한 도메인은 확인되지 않고 메일을 라우팅하는 데 사용할 수 없지만 도메인을 추가한 후에는 도메인을 확인하는 데 필요한 정보를 수집하고 최종적으로 새 테넌트의 MX 레코드를 업데이트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-144">These domains won't be verified and can't be used to route mail, but after the domains are added, you can collect the information needed to verify the domains and eventually update your MX records for the new tenant.</span></span>

```PowerShell
#***********************************************************************
# Login to Azure Active Directory
#*****************************************************************************
$msolcred = Get-Credential
connect-msolservice -credential $msolcred
#****************************************************************************
# Add domains
#****************************************************************************
$Domains = Import-Clixml ".\Domains.xml"
Foreach ($domain in $Domains) {
    New-MsolDomain -Name $domain.Name
}
```

<span data-ttu-id="ac746-145">이제 대상 조직의 Microsoft 365 관리 센터에서 정보를 검토하고 수집하여 시간이 다가오면 도메인을 빠르게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-145">Now you can review and collect the information from the Microsoft 365 admin center of your target organization so you can quickly verify your domains when the time comes:</span></span>

1. <span data-ttu-id="ac746-146">Microsoft 365 관리 센터에 <https://portal.office.com> 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-146">Sign in to the Microsoft 365 admin center at <https://portal.office.com>.</span></span>

2. <span data-ttu-id="ac746-147">**도메인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-147">Click **Domains**.</span></span>

   <span data-ttu-id="ac746-148">도메인이 없는 경우 탐색 사용자 **지정을** 클릭하고 설치 프로그램을 선택한 다음 저장을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="ac746-148">If you don't see domains, click **Customize navigation**, select **Setup**, and then click **Save**.</span></span>

3. <span data-ttu-id="ac746-149">**설정 시작** 링크를 클릭하고 설정 마법사를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-149">Click each **Start setup** link, and then proceed through the setup wizard.</span></span>

4. <span data-ttu-id="ac746-150">**소유권 확인** 페이지의 **이 단계를 수행하는 단계별 지침 참조** 에서 **일반 지침** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-150">On the **Confirm ownership** page, for **See step-by-step instructions for performing this step with**, select **General instructions**.</span></span>

5. <span data-ttu-id="ac746-151">도메인을 확인하는 데 사용할 MX 레코드 또는 TXT 레코드를 기록하고 설정 마법사를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-151">Record the MX record or TXT record that you'll use to verify your domain, and finish the setup wizard.</span></span>

6. <span data-ttu-id="ac746-152">확인 TXT 레코드를 DNS 레코드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-152">Add the verification TXT records to your DNS records.</span></span> <span data-ttu-id="ac746-153">그러면 원본 조직이 대상 조직에서 제거된 후 해당 원본 조직의 도메인을 보다 신속하게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-153">This will let you more quickly verify the domains in the source organization after they're removed from the target organization.</span></span> <span data-ttu-id="ac746-154">DNS 구성에 대한 자세한 내용은 모든 DNS 호스팅 공급자에서 [Microsoft 365용 DNS 레코드 만들기를 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)</span><span class="sxs-lookup"><span data-stu-id="ac746-154">For more information about configuring DNS, see [Create DNS records at any DNS hosting provider for Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

## <a name="step-3-force-senders-to-queue-mail"></a><span data-ttu-id="ac746-155">3단계: 보낸 사람이 메일을 강제로 큐에 넣도록 설정 </span><span class="sxs-lookup"><span data-stu-id="ac746-155">Step 3: Force senders to queue mail</span></span>

<span data-ttu-id="ac746-p113">테넌트 간에 도메인을 이동하는 동안 원본 조직에서 도메인을 삭제한 후 대상 조직에서 해당 도메인을 확인해야 합니다. 그 동안에는 EOP를 통해 메일을 라우팅할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-p113">While moving your domains from one tenant to another, you'll need to delete the domains from the source organization and then verify them in your target organization. During this time, you won't be able to route mail through EOP.</span></span>

<span data-ttu-id="ac746-158">보낸 사람이 메일을 강제로 큐에 넣도록 설정하는 한 가지 옵션은 온-프레미스 메일 서버를 직접 가리키도록 MX 레코드를 업데이트하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-158">One option to force senders to queue mail is to update your MX records to point directly to your on-premises mail server.</span></span>

<span data-ttu-id="ac746-p114">또 다른 옵션은 도메인의 DNS 레코드가 유지(DNS 호스팅 서비스라고도 함)되는 각 도메인에 잘못된 MX 레코드를 두는 것입니다. 이렇게 하면 보낸 사람이 메일을 큐에 넣고 다시 시도하게 됩니다(일반적으로 48시간 동안 다시 시도되지만 이는 공급자마다 다를 수 있음). invalid.outlook.com을 잘못된 MX 대상으로 사용할 수 있습니다. MX 레코드에서 TTL(Time to Live) 값을 5분으로 낮추면 변경 내용을 DNS 공급자에 보다 신속하게 전파할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-p114">Another option is to put an invalid MX record in each domain where the DNS records for your domain are kept (also known as your DNS hosting service). This will cause the sender to queue your mail and retry (typical retry attempts are for 48 hours, but this might vary from provider to provider). You can use invalid.outlook.com as an invalid MX target. Lowering the Time to Live (TTL) value to five minutes on the MX record will help the change propagate to DNS providers more quickly.</span></span>

<span data-ttu-id="ac746-163">DNS 구성에 대한 자세한 내용은 모든 DNS 호스팅 공급자에서 [Microsoft 365용 DNS 레코드 만들기를 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)</span><span class="sxs-lookup"><span data-stu-id="ac746-163">For more information about configuring DNS, see [Create DNS records at any DNS hosting provider for Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ac746-p115">공급자마다 메일이 큐에서 유지되는 기간이 다릅니다. 큐 시간이 만료된 경우 배달 못 함 보고서(NDR)가 보낸 사람에게 전송되지 않도록 하려면 새 테넌트를 신속하게 설정하고 DNS 설정을 되돌려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-p115">Different providers queue mail for different periods of time. You'll need to set up your new tenant quickly and revert your DNS settings to avoid non-delivery reports (NDRs) from being sent to the sender if the queuing time expires.</span></span>

## <a name="step-4-remove-users-groups-and-domains-from-the-source-organization"></a><span data-ttu-id="ac746-166">4단계: 원본 조직에서 사용자, 그룹 및 도메인 제거</span><span class="sxs-lookup"><span data-stu-id="ac746-166">Step 4: Remove users, groups, and domains from the source organization</span></span>

<span data-ttu-id="ac746-167">다음 스크립트는 Azure Active Directory PowerShell을 사용하여 원본 테넌트에서 사용자, 그룹 및 도메인을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-167">The following script removes users, groups, and domains from the source tenant by using Azure Active Directory PowerShell.</span></span> <span data-ttu-id="ac746-168">메모장과 같은 텍스트 편집기에 다음 텍스트를 복사하여 붙여넣고 파일을 C:\EOP\Export\Remove_Users_and_Groups.ps1로 저장한 후 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-168">Copy and paste the following text into a text editor like Notepad, save the file as C:\EOP\Export\Remove_Users_and_Groups.ps1, and run the following command:</span></span>

```PowerShell
& "C:\EOP\Export\Remove_Users_and_Groups.ps1"
```

```PowerShell
#*****************************************************************************
# Login to Azure Active Directory
#*****************************************************************************
$msolcred= Get-Credential
connect-msolservice -credential $msolcred
#*****************************************************************************
# Remove users
#*****************************************************************************
$Users = Get-MSOLUser -All | sort UserPrincipalName
$user_count = $Users.count
write-host "Removing $user_count users."
Foreach ($User in $Users) {
write-host $User.UserPrincipalName
$User | Remove-MSOLUser -Force
}
#*****************************************************************************
# Remove groups
#*****************************************************************************
Get-MSOLGroup | Remove-MSOLGroup -Force
#*****************************************************************************
# Remove domains
# Note: Your onmicrosoft.com domain should be the default domain
#*****************************************************************************
$Domains = Get-MsolDomain
$Domain_count = $Domains.count
write-host "Removing $Domain_count domains."
Foreach ($Domain in $Domains) {
write-host $Domain.Name
Remove-MsolDomain -DomainName $Domain.Name -Force
}
```

## <a name="step-5-verify-domains-for-the-target-organization"></a><span data-ttu-id="ac746-169">5단계: 대상 조직에 대한 도메인 확인</span><span class="sxs-lookup"><span data-stu-id="ac746-169">Step 5: Verify domains for the target organization</span></span>

1. <span data-ttu-id="ac746-170">의 관리 센터에 <https://portal.office.com> 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-170">Sign in to the admin center at <https://portal.office.com>.</span></span>

2. <span data-ttu-id="ac746-171">**도메인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-171">Click **Domains**.</span></span>

3. <span data-ttu-id="ac746-172">대상 도메인에 대한 각 **설정 시작** 링크를 클릭하고 설정 마법사를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-172">Click each **Start setup** link for the target domain and proceed through the setup wizard.</span></span>

## <a name="step-6-add-mail-users-and-groups-to-the-target-organization"></a><span data-ttu-id="ac746-173">6단계: 대상 조직에 메일 사용자 및 그룹 추가</span><span class="sxs-lookup"><span data-stu-id="ac746-173">Step 6: Add mail users and groups to the target organization</span></span>

<span data-ttu-id="ac746-174">EOP에서는 Azure Active Directory를 사용하여 온-프레미스 Active Directory를 대상 테넌트와 동기화하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-174">A best practice for EOP is to use Azure Active Directory to sync your on-premises Active Directory to your target tenant.</span></span> <span data-ttu-id="ac746-175">이 작업을 수행하는 방법에 대한 자세한 내용은 [EOP에서 메일 사용자 관리](manage-mail-users-in-eop.md)에서 "디렉터리 동기화를 사용하여 메일 사용자 관리"를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac746-175">For more information about how to do this, see "Use directory synchronization to manage mail users" in [Manage mail users in EOP](manage-mail-users-in-eop.md).</span></span> <span data-ttu-id="ac746-176">다음 스크립트를 사용하여 원본 테넌트에서 사용자 및 그룹을 다시 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-176">You can also use the following script to recreate your users and groups from your source tenant.</span></span> <span data-ttu-id="ac746-177">참고: 사용자 암호는 이동할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-177">Note: User passwords cannot be moved.</span></span> <span data-ttu-id="ac746-178">새 사용자 암호가 생성되고 UsersAndGroups.ps1이라는 파일에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-178">New user passwords are created and saved in the file named UsersAndGroups.ps1.</span></span>

<span data-ttu-id="ac746-179">스크립트를 사용하려면 메모장과 같은 텍스트 편집기에 다음 텍스트를 복사하여 붙여넣고 파일을 C:\EOP\Export\Add_Users_and_Groups.ps1로 저장한 후 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-179">To use the script, copy and paste the following text into a text editor like Notepad, save the file as C:\EOP\Export\Add_Users_and_Groups.ps1, and run the following command:</span></span>

```PowerShell
& "C:\EOP\Export\Add_Users_and_Groups.ps1"
```

```PowerShell
#***********************************************************************
# makeparam helper function
#****************************************************************************
function makeparam ([string]$ParamName, [string[]] $ParamValue) {
    $FormattedParam = ""
    If($ParamValue.Count -gt 0) {
        $FormattedParam = " -$ParamName "
        Foreach ($value in $ParamValue) {
        If($value -eq "True") {$FormattedParam = " -$ParamName" + ":`$True,"}
        else{
            If($value -eq "False") {$FormattedParam = " -$ParamName" + ":`$False,"}
                else{$FormattedParam += "`"$value`","}
            }
        }
        $FormattedParam = $FormattedParam.TrimEnd(",")
    }
    Return $FormattedParam
 }
#****************************************************************************
# Variables
#****************************************************************************
$outfile = ".\UsersAndGroups.ps1"
rm -erroraction 'silentlycontinue' $outfile
#****************************************************************************
# Add mail users
#****************************************************************************
$rand = New-Object System.Random -ArgumentList (get-date).millisecond
$MailUsers = Import-Clixml ".\MailUsers.xml"
$MailUsersCount = $MailUsers.Name.Count
if($MailUsersCount -gt 0){
    Write-Host "Importing $MailUsersCount Mail Users"
    ForEach ($MailUser in $MailUsers) {
        $MailUsersCmdlet = "New-MailUser"
        If((Get-PSSession).ComputerName.Contains("ps.protection")) {
            $DistributionGroupsCmdlet = "New-EOPMailUser"
        }
        $MailUsersCmdlet += makeparam "LastName" $MailUser.LastName
        $MailUsersCmdlet += makeparam "FirstName" $MailUser.FirstName
        $MailUsersCmdlet += makeparam "DisplayName" $MailUser.DisplayName
        $MailUsersCmdlet += makeparam "Name" $MailUser.Name
        $MailUsersCmdlet += makeparam "Alias" $MailUser.Alias
        $MailUsersCmdlet += makeparam "MicrosoftOnlineServicesID" $MailUser.MicrosoftOnlineServicesID
        $MailUsersCmdlet += makeparam "ExternalEmailAddress" $MailUser.ExternalEmailAddress

        # Generate a new 10 character password
        $NewPassword = ""
        1..10 | ForEach { $NewPassword = $NewPassword + [char]$rand.next(40,127) }

        $MailUsersCmdlet += " -Password (ConvertTo-SecureString -String '$NewPassword' -AsPlainText -Force)"
        Add-Content $outfile "`n$MailUsersCmdlet"
    }
}
#****************************************************************************
# Add distribution groups
#****************************************************************************
$DistributionGroups = Import-Clixml ".\DistributionGroups.xml"
$DistributionGroupsCount = $DistributionGroups.Name.Count
if($DistributionGroupsCount -gt 0){
    Write-Host "Importing $DistributionGroupsCount Distribution Groups"
    ForEach ($DistributionGroup in $DistributionGroups) {
        $DistributionGroupsCmdlet = "New-DistributionGroup"
        If((Get-PSSession).ComputerName.Contains("ps.protection")) {
            $DistributionGroupsCmdlet = "New-EOPDistributionGroup"
        }
        $DistributionGroupsCmdlet += makeparam "Name" $DistributionGroup.Name
        $DistributionGroupsCmdlet += makeparam "Alias" $DistributionGroup.Alias
        $DistributionGroupsCmdlet += makeparam "DisplayName" $DistributionGroup.DisplayName
        $DistributionGroupsCmdlet += makeparam "ManagedBy" $DistributionGroup.ManagedBy

        $DistributionGroupsCmdlet += makeparam "Notes" $DistributionGroup.Notes
        $DistributionGroupsCmdlet += makeparam "PrimarySmtpAddress" $DistributionGroup.PrimarySmtpAddress
        $DistributionGroupsCmdlet += makeparam "Type" $DistributionGroup.Type
        $MembersCmdlet = "@("
        $memberslist = Import-Clixml $DistributionGroup.ExternalDirectoryObjectId
        ForEach ($user in $memberslist) {
            $MembersCmdlet += "`"$user.Name`","
        }
        $MembersCmdlet = $MembersCmdlet.TrimEnd(",")
        $MembersCmdlet += ")"
    }
    Add-Content $outfile "`n$DistributionGroupsCmdlet"
}
#****************************************************************************
# Add security groups
#****************************************************************************
$SecurityGroups = Import-Clixml ".\SecurityGroups.xml"
$SecurityGroupsCount = $SecurityGroups.Name.Count
if($SecurityGroupsCount -gt 0){
    Write-Host "Importing $SecurityGroupsCount Security Groups"
    ForEach ($SecurityGroup in $SecurityGroups) {
        $SecurityGroupsCmdlet = "New-SecurityGroup"
        If((Get-PSSession).ComputerName.Contains("ps.protection")) {
            $DistributionGroupsCmdlet = "New-EOPSecurityGroup"
        }
        $SecurityGroupsCmdlet += makeparam "Name" $SecurityGroup.Name
        $SecurityGroupsCmdlet += makeparam "Alias" $SecurityGroup.Alias
        $SecurityGroupsCmdlet += makeparam "DisplayName" $SecurityGroup.DisplayName
        $SecurityGroupsCmdlet += makeparam "ManagedBy" $SecurityGroup.ManagedBy

        $SecurityGroupsCmdlet += makeparam "Notes" $SecurityGroup.Notes
        $SecurityGroupsCmdlet += makeparam "PrimarySmtpAddress" $SecurityGroup.PrimarySmtpAddress
        $SecurityGroupsCmdlet += makeparam "Type" $SecurityGroup.Type
        $MembersCmdlet = "@("
        $memberslist = Import-Clixml $SecurityGroup.ExternalDirectoryObjectId
        ForEach ($user in $memberslist) {
            $MembersCmdlet += "`"$user.Name`","
        }
        $MembersCmdlet = $MembersCmdlet.TrimEnd(",")
        $MembersCmdlet += ")"
    }
    Add-Content $outfile "`n$SecurityGroupsCmdlet"
}
#****************************************************************************
# Add Dynamic Distribution Groups
#****************************************************************************
If((Get-PSSession).ComputerName.Contains("ps.protection")) {
    write-Host "No Synamic Distribution Groups for EOP Standard organizations."
}else{
    $DynamicDistributionGroups = Import-Clixml ".\DynamicDistributionGroups.xml"
    $DynamicDistributionGroupsCount = $DynamicDistributionGroups.Name.Count
    if($DynamicDistributionGroupsCount -gt 0){
        Write-Host "Importing $DynamicDistributionGroupsCount Dynamic Distribution Groups"
        foreach ($DynamicDistributionGroup in $DynamicDistributionGroups) {
            $DynamicDistributionGroupsCmdlet = "New-DynamicDistributionGroup"
            $DynamicDistributionGroupsCmdlet += " -Confirm:`$False"
            $DynamicDistributionGroupsCmdlet += makeparam "DisplayName" $DynamicDistributionGroup.DisplayName
            $DynamicDistributionGroupsCmdlet += makeparam "ModeratedBy" $DynamicDistributionGroup.ModeratedBy
            $DynamicDistributionGroupsCmdlet += makeparam "ModerationEnabled" $DynamicDistributionGroup.ModerationEnabled
            $DynamicDistributionGroupsCmdlet += makeparam "Name" $DynamicDistributionGroup.Name
            $DynamicDistributionGroupsCmdlet += makeparam "PrimarySmtpAddress" $DynamicDistributionGroup.PrimarySmtpAddress
            $DynamicDistributionGroupsCmdlet += makeparam "RecipientContainer" $DynamicDistributionGroup.RecipientContainer
            $RecipientFilterParam =  makeparam "RecipientFilter" $DynamicDistributionGroup.RecipientFilter
            $RecipientFilterParam = " -RecipientFilter {" + $RecipientFilterParam.Substring(19)
            $RecipientFilterParam = $RecipientFilterParam.Substring(0,$RecipientFilterParam.Length-1)
            $RecipientFilterParam += "}"
            $DynamicDistributionGroupsCmdlet +=  $RecipientFilterParam
            $DynamicDistributionGroupsCmdlet += makeparam "SendModerationNotifications" $DynamicDistributionGroup.SendModerationNotifications
            Add-Content $outfile "`n$DynamicDistributionGroupsCmdlet"
        }

    }else{
        Write-Host "No Dynamic Distribution Groups to add."
    }
}
#****************************************************************************
# Add Mail Contacts
#****************************************************************************
If((Get-PSSession).ComputerName.Contains("ps.protection")) {
    write-Host "No Mail Contact for EOP Standard organizations."
}else{
    $MailContacts = Import-Clixml ".\MailContacts.xml"
    $MailContactsCount = $MailContacts.Name.Count
    if($MailContactsCount -gt 0){
        Write-Host "Importing $MailContactsCount Dynamic Distribution Groups"
        foreach ($MailContact in $MailContacts) {
            $MailContactsCmdlet = "New-MailContact"
            $MailContactsCmdlet += makeparam "UsePreferMessageFormat" $MailContact.UsePreferMessageFormat
            $MailContactsCmdlet += makeparam "DisplayName" $MailContact.DisplayName
            $MailContactsCmdlet += makeparam "ModeratedBy" $MailContact.ModeratedBy
            $MailContactsCmdlet += makeparam "Name" $MailContact.Name
            $MailContactsCmdlet += makeparam "MessageBodyFormat" $MailContact.MessageBodyFormat
            $MailContactsCmdlet += makeparam "OrganizationalUnit" $MailContact.OrganizationalUnit
            $MailContactsCmdlet += makeparam "Initials" $MailContact.Initials
            $MailContactsCmdlet += makeparam "MessageFormat" $MailContact.MessageFormat
            $MailContactsCmdlet += makeparam "ModerationEnabled" $MailContact.ModerationEnabled
            $MailContactsCmdlet += makeparam "MacAttachmentFormat" $MailContact.MacAttachmentFormat
            $MailContactsCmdlet += makeparam "SendModerationNotifications" $MailContact.SendModerationNotifications
            $MailContactsCmdlet += " -Confirm:`$False"
            $MailContactsCmdlet += makeparam "ExternalEmailAddress" $MailContact.ExternalEmailAddress
            $MailContactsCmdlet += makeparam "FirstName" $MailContact.FirstName
            $MailContactsCmdlet += makeparam "Alias" $MailContact.Alias
            Add-Content $outfile "`n$MailContactsCmdlet"
        }

    }else{
        Write-Host "No Mail Contacts to add."
    }
}
#***********************************************************************
# makeparam helper function
#************************************************************************
 function makeparam ([string]$ParamName, [string[]] $ParamValue) {
    $FormattedParam = ""
    If($ParamValue.Count -gt 0) {
        $FormattedParam = " -$ParamName "
        Foreach ($value in $ParamValue) {
        If($value -eq "True") {$FormattedParam = " -$ParamName" + ":`$True,"}
        else{
            If($value -eq "False") {$FormattedParam = " -$ParamName" + ":`$False,"}
                else{$FormattedParam += "`"$value`","}
            }
        }
        $FormattedParam = $FormattedParam.TrimEnd(",")
    }
    Return $FormattedParam
 }
#****************************************************************************
# Variables
#****************************************************************************
$outfile = ".\UsersAndGroups.ps1"
rm -erroraction 'silentlycontinue' $outfile
#****************************************************************************
# Add mail users
#****************************************************************************
$rand = New-Object System.Random -ArgumentList (get-date).millisecond
$MailUsers = Import-Clixml ".\MailUsers.xml"
$MailUsersCount = $MailUsers.Name.Count
if($MailUsersCount -gt 0){
    Write-Host "Importing $MailUsersCount Mail Users"
    ForEach ($MailUser in $MailUsers) {
        $MailUsersCmdlet = "New-EOPMailUser"
        $MailUsersCmdlet += makeparam "LastName" $MailUser.LastName
        $MailUsersCmdlet += makeparam "FirstName" $MailUser.FirstName
        $MailUsersCmdlet += makeparam "DisplayName" $MailUser.DisplayName
        $MailUsersCmdlet += makeparam "Name" $MailUser.Name
        $MailUsersCmdlet += makeparam "Alias" $MailUser.Alias
        $MailUsersCmdlet += makeparam "MicrosoftOnlineServicesID" $MailUser.MicrosoftOnlineServicesID
        $MailUsersCmdlet += makeparam "ExternalEmailAddress" $MailUser.ExternalEmailAddress

        # Generate a new 10 character password
        $NewPassword = ""
        1..10 | ForEach { $NewPassword = $NewPassword + [char]$rand.next(40,127) }

        $MailUsersCmdlet += " -Password (ConvertTo-SecureString -String '$NewPassword' -AsPlainText -Force)"
        Add-Content $outfile "`n$MailUsersCmdlet"
    }
}
#****************************************************************************
# Add distribution groups
#****************************************************************************
$DistributionGroups = Import-Clixml ".\DistributionGroups.xml"
$DistributionGroupsCount = $DistributionGroups.Name.Count
if($DistributionGroupsCount -gt 0){
    Write-Host "Importing $DistributionGroupsCount Distribution Groups"
    ForEach ($DistributionGroup in $DistributionGroups) {
        $DistributionGroupsCmdlet = "New-EOPDistributionGroup"
        $DistributionGroupsCmdlet += makeparam "Name" $DistributionGroup.Name
        $DistributionGroupsCmdlet += makeparam "Alias" $DistributionGroup.Alias
        $DistributionGroupsCmdlet += makeparam "DisplayName" $DistributionGroup.DisplayName
        $DistributionGroupsCmdlet += makeparam "ManagedBy" $DistributionGroup.ManagedBy

        $DistributionGroupsCmdlet += makeparam "Notes" $DistributionGroup.Notes
        $DistributionGroupsCmdlet += makeparam "PrimarySmtpAddress" $DistributionGroup.PrimarySmtpAddress
        $DistributionGroupsCmdlet += makeparam "Type" $DistributionGroup.Type
        $MembersCmdlet = "@("
        $memberslist = Import-Clixml $DistributionGroup.ExternalDirectoryObjectId
        ForEach ($user in $memberslist) {
            $MembersCmdlet += "`"$user.Name`","
        }
        $MembersCmdlet = $MembersCmdlet.TrimEnd(",")
        $MembersCmdlet += ")"
    }
    Add-Content $outfile "`n$DistributionGroupsCmdlet"
}
#****************************************************************************
# Add security groups
#****************************************************************************
$SecurityGroups = Import-Clixml ".\SecurityGroups.xml"
$SecurityGroupsCount = $SecurityGroups.Name.Count
if($SecurityGroupsCount -gt 0){
    Write-Host "Importing $SecurityGroupsCount Security Groups"
    ForEach ($SecurityGroup in $SecurityGroups) {
        $SecurityGroupsCmdlet = "New-EOPSecurityGroup"
        $SecurityGroupsCmdlet += makeparam "Name" $SecurityGroup.Name
        $SecurityGroupsCmdlet += makeparam "Alias" $SecurityGroup.Alias
        $SecurityGroupsCmdlet += makeparam "DisplayName" $SecurityGroup.DisplayName
        $SecurityGroupsCmdlet += makeparam "ManagedBy" $SecurityGroup.ManagedBy

        $SecurityGroupsCmdlet += makeparam "Notes" $SecurityGroup.Notes
        $SecurityGroupsCmdlet += makeparam "PrimarySmtpAddress" $SecurityGroup.PrimarySmtpAddress
        $SecurityGroupsCmdlet += makeparam "Type" $SecurityGroup.Type
        $MembersCmdlet = "@("
        $memberslist = Import-Clixml $SecurityGroup.ExternalDirectoryObjectId
        ForEach ($user in $memberslist) {
            $MembersCmdlet += "`"$user.Name`","
        }
        $MembersCmdlet = $MembersCmdlet.TrimEnd(",")
        $MembersCmdlet += ")"
    }
    Add-Content $outfile "`n$SecurityGroupsCmdlet"
}
#****************************************************************************
# Add Dynamic Distribution Groups
#****************************************************************************
$DynamicDistributionGroups = Import-Clixml ".\DynamicDistributionGroups.xml"
$DynamicDistributionGroupsCount = $DynamicDistributionGroups.Name.Count
if($DynamicDistributionGroupsCount -gt 0){
    Write-Host "Importing $DynamicDistributionGroupsCount Dynamic Distribution Groups"
    foreach ($DynamicDistributionGroup in $DynamicDistributionGroups) {
        $DynamicDistributionGroupsCmdlet = "New-DynamicDistributionGroup"
        $DynamicDistributionGroupsCmdlet += " -Confirm:`$False"
        $DynamicDistributionGroupsCmdlet += makeparam "DisplayName" $DynamicDistributionGroup.DisplayName
        $DynamicDistributionGroupsCmdlet += makeparam "ModeratedBy" $DynamicDistributionGroup.ModeratedBy
        $DynamicDistributionGroupsCmdlet += makeparam "ModerationEnabled" $DynamicDistributionGroup.ModerationEnabled
        $DynamicDistributionGroupsCmdlet += makeparam "Name" $DynamicDistributionGroup.Name
        $DynamicDistributionGroupsCmdlet += makeparam "PrimarySmtpAddress" $DynamicDistributionGroup.PrimarySmtpAddress
        $DynamicDistributionGroupsCmdlet += makeparam "RecipientContainer" $DynamicDistributionGroup.RecipientContainer
        $RecipientFilterParam =  makeparam "RecipientFilter" $DynamicDistributionGroup.RecipientFilter
        $RecipientFilterParam = " -RecipientFilter {" + $RecipientFilterParam.Substring(19)
        $RecipientFilterParam = $RecipientFilterParam.Substring(0,$RecipientFilterParam.Length-1)
        $RecipientFilterParam += "}"
        $DynamicDistributionGroupsCmdlet +=  $RecipientFilterParam
        $DynamicDistributionGroupsCmdlet += makeparam "SendModerationNotifications" $DynamicDistributionGroup.SendModerationNotifications
        Add-Content $outfile "`n$DynamicDistributionGroupsCmdlet"
    }

}else{
    Write-Host "No Dynamic Distribution Groups to add."
}
#****************************************************************************
# Add Mail Contacts
#****************************************************************************
$MailContacts = Import-Clixml ".\MailContacts.xml"
$MailContactsCount = $MailContacts.Name.Count
if($MailContactsCount -gt 0){
    Write-Host "Importing $MailContactsCount Dynamic Distribution Groups"
    foreach ($MailContact in $MailContacts) {
        $MailContactsCmdlet = "New-MailContact"
        $MailContactsCmdlet += makeparam "UsePreferMessageFormat" $MailContact.UsePreferMessageFormat
        $MailContactsCmdlet += makeparam "DisplayName" $MailContact.DisplayName
        $MailContactsCmdlet += makeparam "ModeratedBy" $MailContact.ModeratedBy
        $MailContactsCmdlet += makeparam "Name" $MailContact.Name
        $MailContactsCmdlet += makeparam "MessageBodyFormat" $MailContact.MessageBodyFormat
        $MailContactsCmdlet += makeparam "OrganizationalUnit" $MailContact.OrganizationalUnit
        $MailContactsCmdlet += makeparam "Initials" $MailContact.Initials
        $MailContactsCmdlet += makeparam "MessageFormat" $MailContact.MessageFormat
        $MailContactsCmdlet += makeparam "ModerationEnabled" $MailContact.ModerationEnabled
        $MailContactsCmdlet += makeparam "MacAttachmentFormat" $MailContact.MacAttachmentFormat
        $MailContactsCmdlet += makeparam "SendModerationNotifications" $MailContact.SendModerationNotifications
        $MailContactsCmdlet += " -Confirm:`$False"
        $MailContactsCmdlet += makeparam "ExternalEmailAddress" $MailContact.ExternalEmailAddress
        $MailContactsCmdlet += makeparam "FirstName" $MailContact.FirstName
        $MailContactsCmdlet += makeparam "Alias" $MailContact.Alias
        Add-Content $outfile "`n$MailContactsCmdlet"
    }

}else{
    Write-Host "No Mail Contacts to add."
}
```

## <a name="step-7-add-protection-settings-to-the-target-organization"></a><span data-ttu-id="ac746-180">7단계: 대상 조직에 보호 설정 추가</span><span class="sxs-lookup"><span data-stu-id="ac746-180">Step 7: Add protection settings to the target organization</span></span>

<span data-ttu-id="ac746-181">대상 조직에 로그인되어 있는 동안 Export 디렉터리에서 다음 스크립트를 실행하여 이전에 원본 조직에서 .xml 파일로 내보낸 설정을 다시 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-181">You can run the following script from the Export directory while logged in to your target organization to recreate the settings exported to .xml files earlier from the source organization.</span></span>

<span data-ttu-id="ac746-182">메모장과 같은 텍스트 편집기에 스크립트 텍스트를 복사하여 붙여넣고 파일을 C:\EOP\Export\Import_Settings.ps1로 저장한 후 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-182">Copy and paste the script text into a text editor like Notepad, save the file as C:\EOP\Export\Import_Settings.ps1, and run the following command:</span></span>

```PowerShell
& "C:\EOP\Export\Import_Settings.ps1"
```

<span data-ttu-id="ac746-183">이 스크립트는 .xml 파일을 가져와 Settings.ps1이라는 Windows PowerShell 스크립트 파일을 만듭니다. 이 파일을 검토하고 편집한 후 실행하여 보호 및 메일 흐름 설정을 다시 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac746-183">This script imports the .xml files and create a Windows PowerShell script file called Settings.ps1 that you can review, edit, and then run to recreate your protection and mail-flow settings.</span></span>

```PowerShell
#***********************************************************************
# makeparam helper function
#****************************************************************************
 function makeparam ([string]$ParamName, [string[]] $ParamValue) {
    $FormattedParam = ""
    If($ParamValue.Count -gt 0) {
        $FormattedParam = " -$ParamName "
        Foreach ($value in $ParamValue) {
        If($value -eq "True") {$FormattedParam = " -$ParamName" + ":`$True,"}
        else{
            If($value -eq "False") {$FormattedParam = " -$ParamName" + ":`$False,"}
                else{$FormattedParam += "`"$value`","}
            }
        }
        $FormattedParam = $FormattedParam.TrimEnd(",")
    }
    Return $FormattedParam
 }
#****************************************************************************
# Variables
#****************************************************************************
$outfile = ".\Settings.ps1"
rm -erroraction 'silentlycontinue' $outfile
#****************************************************************************
# HostedContentFilterPolicy
#****************************************************************************
$HostedContentFilterPolicies = Import-Clixml ".\HostedContentFilterPolicy.xml"
$HostedContentFilterPolicyCount = $HostedContentFilterPolicies.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $HostedContentFilterPolicyCount Inbound Connectors"
    ForEach ($HostedContentFilterPolicy in $HostedContentFilterPolicies) {
        $HostedContentFilterPolicyCmdlet = "New-HostedContentFilterPolicy"
        if($HostedContentFilterPolicy.Name -eq "Default") {$HostedContentFilterPolicyCmdlet = "Set-HostedContentFilterPolicy -Identity Default"}
        else {
        $HostedContentFilterPolicyCmdlet += makeparam "Name" $HostedContentFilterPolicy.Name
        }
        $HostedContentFilterPolicyCmdlet += makeparam "AddXHeaderValue" $HostedContentFilterPolicy.AddXHeaderValue
        $HostedContentFilterPolicyCmdlet += makeparam "AdminDisplayName" $HostedContentFilterPolicy.AdminDisplayName
        $HostedContentFilterPolicyCmdlet += " -Confirm:`$False"
        $HostedContentFilterPolicyCmdlet += makeparam "DownloadLink" $HostedContentFilterPolicy.DownloadLink
        $HostedContentFilterPolicyCmdlet += makeparam "EnableEndUserSpamNotifications" $HostedContentFilterPolicy.EnableEndUserSpamNotifications
        $HostedContentFilterPolicyCmdlet += makeparam "EnableLanguageBlockList" $HostedContentFilterPolicy.EnableLanguageBlockList
        $HostedContentFilterPolicyCmdlet += makeparam "EnableRegionBlockList" $HostedContentFilterPolicy.EnableRegionBlockList
        if($HostedContentFilterPolicy.EndUserSpamNotificationCustomFromAddress.Length -gt 0)
        {
            $HostedContentFilterPolicyCmdlet += makeparam "EndUserSpamNotificationCustomFromAddress" $HostedContentFilterPolicy.EndUserSpamNotificationCustomFromAddress
        }
        $HostedContentFilterPolicyCmdlet += makeparam "EndUserSpamNotificationCustomFromName" $HostedContentFilterPolicy.EndUserSpamNotificationCustomFromName
        $HostedContentFilterPolicyCmdlet += makeparam "EndUserSpamNotificationCustomSubject" $HostedContentFilterPolicy.EndUserSpamNotificationCustomSubject
        $HostedContentFilterPolicyCmdlet += makeparam "EndUserSpamNotificationFrequency" $HostedContentFilterPolicy.EndUserSpamNotificationFrequency
        $HostedContentFilterPolicyCmdlet += makeparam "EndUserSpamNotificationLanguage" $HostedContentFilterPolicy.EndUserSpamNotificationLanguage
        $HostedContentFilterPolicyCmdlet += makeparam "LanguageBlockList" $HostedContentFilterPolicy.LanguageBlockList
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamBulkMail" $HostedContentFilterPolicy.MarkAsSpamBulkMail
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamEmbedTagsInHtml" $HostedContentFilterPolicy.MarkAsSpamEmbedTagsInHtml
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamEmptyMessages" $HostedContentFilterPolicy.MarkAsSpamEmptyMessages
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamFormTagsInHtml" $HostedContentFilterPolicy.MarkAsSpamFormTagsInHtml
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamFramesInHtml" $HostedContentFilterPolicy.MarkAsSpamFramesInHtml
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamFromAddressAuthFail" $HostedContentFilterPolicy.MarkAsSpamFromAddressAuthFail
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamJavaScriptInHtml" $HostedContentFilterPolicy.MarkAsSpamJavaScriptInHtml
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamNdrBackscatter" $HostedContentFilterPolicy.MarkAsSpamNdrBackscatter
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamObjectTagsInHtml" $HostedContentFilterPolicy.MarkAsSpamObjectTagsInHtml
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamSensitiveWordList" $HostedContentFilterPolicy.MarkAsSpamSensitiveWordList
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamSpfRecordHardFail" $HostedContentFilterPolicy.MarkAsSpamSpfRecordHardFail
        $HostedContentFilterPolicyCmdlet += makeparam "MarkAsSpamWebBugsInHtml" $HostedContentFilterPolicy.MarkAsSpamWebBugsInHtml
        $HostedContentFilterPolicyCmdlet += makeparam "ModifySubjectValue" $HostedContentFilterPolicy.ModifySubjectValue
        $HostedContentFilterPolicyCmdlet += makeparam "Organization" $HostedContentFilterPolicy.Organization
        $HostedContentFilterPolicyCmdlet += makeparam "QuarantineRetentionPeriod" $HostedContentFilterPolicy.QuarantineRetentionPeriod
        $HostedContentFilterPolicyCmdlet += makeparam "RedirectToRecipients" $HostedContentFilterPolicy.RedirectToRecipients
        $HostedContentFilterPolicyCmdlet += makeparam "RegionBlockList" $HostedContentFilterPolicy.RegionBlockList
        $HostedContentFilterPolicyCmdlet += makeparam "SpamAction" $HostedContentFilterPolicy.SpamAction
        $HostedContentFilterPolicyCmdlet += makeparam "TestModeBccToRecipients" $HostedContentFilterPolicy.TestModeBccToRecipients
        Add-Content $outfile "`n$HostedContentFilterPolicyCmdlet"
    }
 }else{
    Write-Host "No Hosted Content Policy Filters to add."
 }
#****************************************************************************
# HostedContentFilterRule
#****************************************************************************
$HostedContentFilterRules = Import-Clixml ".\HostedContentFilterRule.xml"
$HostedContentFilterRuleCount = $HostedContentFilterRules.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $HostedContentFilterRuleCount Hosted Content Filter Rules"
    ForEach ($HostedContentFilterRule in $HostedContentFilterRules) {
        $HostedContentFilterRuleCmdlet = "New-HostedContentFilterRule"
        if($HostedContentFilterRule.Name -eq "Default") {$HostedContentFilterRuleCmdlet = "Set-HostedContentFilterRule Default"}
        $HostedContentFilterRuleCmdlet += makeparam "Name" $HostedContentFilterRule.Name
        $HostedContentFilterRuleCmdlet  += makeparam "HostedContentFilterPolicy" $HostedContentFilterRule.HostedContentFilterPolicy
        $HostedContentFilterRuleCmdlet += makeparam "Comments" $HostedContentFilterRule.Comments
        $HostedContentFilterRuleCmdlet += " -Confirm:`$False"
        $HostedContentFilterRuleCmdlet += makeparam "Enabled" $HostedContentFilterRule.Enabled
        $HostedContentFilterRuleCmdlet += makeparam "ExceptIfRecipientDomainIs" $HostedContentFilterRule.ExceptIfRecipientDomainIs
        $HostedContentFilterRuleCmdlet += makeparam "ExceptIfSentTo" $HostedContentFilterRule.ExceptIfSentTo
        $HostedContentFilterRuleCmdlet += makeparam "ExceptIfSentToMemberOf" $HostedContentFilterRule.ExceptIfSentToMemberOf
        $HostedContentFilterRuleCmdlet += makeparam "Priority" $HostedContentFilterRule.Priority
        $HostedContentFilterRuleCmdlet += makeparam "RecipientDomainIs" $HostedContentFilterRule.RecipientDomainIs
        $HostedContentFilterRuleCmdlet += makeparam "SentTo" $HostedContentFilterRule.SentTo
        $HostedContentFilterRuleCmdlet += makeparam "SentToMemberOf" $HostedContentFilterRule.SentToMemberOf
        Add-Content $outfile "`n$HostedContentFilterRuleCmdlet"
    }
 }else{
    Write-Host "No Hosted Content Filter Rules to add."
 }
#****************************************************************************
# HostedOutboundSpamFilterPolicy
#****************************************************************************
$HostedOutboundSpamFilterPolicies = Import-Clixml ".\HostedOutboundSpamFilterPolicy.xml"
$HostedOutboundSpamFilterPolicyCount = $HostedOutboundSpamFilterPolicies.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $HostedOutboundSpamFilterPolicyCount Hosted Outbound Spam Filter Policies"
    ForEach ($HostedOutboundSpamFilterPolicy in $HostedOutboundSpamFilterPolicies) {
        $HostedOutboundSpamFilterPolicyCmdlet = "Set-HostedOutboundSpamFilterPolicy Default"
        $HostedOutboundSpamFilterPolicyCmdlet += makeparam "AdminDisplayName" $HostedOutboundSpamFilterPolicy.AdminDisplayName
        $HostedOutboundSpamFilterPolicyCmdlet += makeparam "BccSuspiciousOutboundAdditionalRecipients"
        $HostedOutboundSpamFilterPolicy.BccSuspiciousOutboundAdditionalRecipients
        $HostedOutboundSpamFilterPolicyCmdlet += makeparam "BccSuspiciousOutboundMail" $HostedOutboundSpamFilterPolicy.BccSuspiciousOutboundMail
        $HostedOutboundSpamFilterPolicyCmdlet += " -Confirm:`$False"
        $HostedOutboundSpamFilterPolicyCmdlet += makeparam "NotifyOutboundSpam" $HostedOutboundSpamFilterPolicy.NotifyOutboundSpam
        $NotifyOutboundSpamRecipients  += makeparam "NotifyOutboundSpamRecipients" $HostedOutboundSpamFilterPolicy.NotifyOutboundSpamRecipients
        Add-Content $outfile "`n$HostedOutboundSpamFilterPolicyCmdlet"
    }
 }else{
    Write-Host "No Hosted Outbound Spam Filter Policies to add."
 }
#****************************************************************************
# HostedConnectionFilterPolicy
#****************************************************************************
$HostedConnectionFilterPolicies = Import-Clixml ".\HostedConnectionFilterPolicy.xml"
$HostedConnectionFilterPolicyCount = $HostedConnectionFilterPolicies.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $HostedConnectionFilterPolicyCount Hosted Connection Filter Policies"
    ForEach ($HostedConnectionFilterPolicy in $HostedConnectionFilterPolicies) {
        $HostedConnectionFilterPolicyCmdlet = "Set-HostedConnectionFilterPolicy"
        $HostedConnectionFilterPolicyCmdlet += makeparam "Identity" $HostedConnectionFilterPolicy.Name
        $HostedConnectionFilterPolicyCmdlet += makeparam "AdminDisplayName" $HostedConnectionFilterPolicy.AdminDisplayName
        $HostedConnectionFilterPolicyCmdlet += " -Confirm:`$False"
        $HostedConnectionFilterPolicyCmdlet += makeparam "EnableSafeList" $HostedConnectionFilterPolicy.EnableSafeList
        $HostedConnectionFilterPolicyCmdlet += makeparam "IPAllowList" $HostedConnectionFilterPolicy.IPAllowList
        $HostedConnectionFilterPolicyCmdlet += makeparam "IPBlockList" $HostedConnectionFilterPolicy.IPBlockList

        Add-Content $outfile "`n$HostedConnectionFilterPolicyCmdlet"
    }
 }else{
    Write-Host "No Hosted Connection Filter Policies to add."
 }
#****************************************************************************
# MalwareFilterPolicy
#****************************************************************************
$MalwareFilterPolicies = Import-Clixml ".\MalwareFilterPolicy.xml"
$MalwareFilterPolicyCount = $MalwareFilterPolicies.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $MalwareFilterPolicyCount Malware Filter Policies"
    ForEach ($MalwareFilterPolicy in $MalwareFilterPolicies) {
        $MalwareFilterPolicyCmdlet = "New-MalwareFilterPolicy"
        if($MalwareFilterPolicy.Name -eq "Default") {$MalwareFilterPolicyCmdlet = "Set-MalwareFilterPolicy Default"}
        else {
        $MalwareFilterPolicyCmdlet += makeparam "Name" $MalwareFilterPolicy.Name
        }
        $MalwareFilterPolicyCmdlet += makeparam "Action" $MalwareFilterPolicy.Action
        $MalwareFilterPolicyCmdlet += makeparam "DeleteAttachmentAndUseDefaultAlertText" $MalwareFilterPolicy.DeleteAttachmentAndUseDefaultAlertText
        $MalwareFilterPolicyCmdlet += makeparam "DeleteAttachmentAndUseCustomAlertText" $MalwareFilterPolicy.DeleteAttachmentAndUseCustomAlertText
        $MalwareFilterPolicyCmdlet += makeparam "AdminDisplayName" $MalwareFilterPolicy.AdminDisplayName
        $MalwareFilterPolicyCmdlet += " -Confirm:`$False"
        $MalwareFilterPolicyCmdlet += makeparam "CustomAlertText" $MalwareFilterPolicy.CustomAlertText
        $MalwareFilterPolicyCmdlet += makeparam "CustomExternalBody" $MalwareFilterPolicy.CustomExternalBody
        $MalwareFilterPolicyCmdlet += makeparam "CustomExternalSubject" $MalwareFilterPolicy.CustomExternalSubject
        if($MalwareFilterPolicy.CustomFromAddress.Length -gt 0) {
            $MalwareFilterPolicyCmdlet += makeparam "CustomFromAddress" $MalwareFilterPolicy.CustomFromAddress
        }
        $MalwareFilterPolicyCmdlet += makeparam "CustomFromName" $MalwareFilterPolicy.CustomFromName
        $MalwareFilterPolicyCmdlet += makeparam "CustomInternalBody" $MalwareFilterPolicy.CustomInternalBody
        $MalwareFilterPolicyCmdlet += makeparam "CustomInternalSubject" $MalwareFilterPolicy.CustomInternalSubject
        $MalwareFilterPolicyCmdlet += makeparam "CustomNotifications" $MalwareFilterPolicy.CustomNotifications
        $MalwareFilterPolicyCmdlet += makeparam "EnableExternalSenderAdminNotifications" $MalwareFilterPolicy.EnableExternalSenderAdminNotifications
        $MalwareFilterPolicyCmdlet += makeparam "EnableExternalSenderNotifications" $MalwareFilterPolicy.EnableExternalSenderNotifications
        $MalwareFilterPolicyCmdlet += makeparam "EnableInternalSenderAdminNotifications" $MalwareFilterPolicy.EnableInternalSenderAdminNotifications
        $MalwareFilterPolicyCmdlet += makeparam "EnableInternalSenderNotifications" $MalwareFilterPolicy.EnableInternalSenderNotifications
        if($MalwareFilterPolicy.ExternalSenderAdminAddress.Length -gt 0) {
        $MalwareFilterPolicyCmdlet += makeparam "ExternalSenderAdminAddress" $MalwareFilterPolicy.ExternalSenderAdminAddress
        }
        if($MalwareFilterPolicy.InternalSenderAdminAddress.Length -gt 0) {
        $MalwareFilterPolicyCmdlet += makeparam "InternalSenderAdminAddress" $MalwareFilterPolicy.InternalSenderAdminAddress
        }
        Add-Content $outfile "`n$MalwareFilterPolicyCmdlet"
    }
 }else{
    Write-Host "No Malware Filter Policies to add."
 }
#****************************************************************************
# MalwareFilterRule
#****************************************************************************
$MalwareFilterRules = Import-Clixml ".\MalwareFilterRule.xml"
$MalwareFilterRuleCount = $MalwareFilterRules.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $MalwareFilterRuleCount Malware Filter Rules"
    ForEach ($MalwareFilterRule in $MalwareFilterRules) {
        $MalwareFilterRuleCmdlet = "New-MalwareFilterRule"
        if($MalwareFilterRule.Name -eq "Default") {$MalwareFilterRuleCmdlet = "Set-MalwareFilterPolicy Default"}
        $MalwareFilterRuleCmdlet += makeparam "Name" $MalwareFilterRule.Name
        $MalwareFilterRuleCmdlet += makeparam "MalwareFilterPolicy" $MalwareFilterRule.MalwareFilterPolicy
        $MalwareFilterRuleCmdlet += makeparam "Comments" $MalwareFilterRule.Comments
        $MalwareFilterRuleCmdlet += " -Confirm:`$False"
        $MalwareFilterRuleCmdlet += makeparam "Enabled" $MalwareFilterRule.Enabled
        $MalwareFilterRuleCmdlet += makeparam "ExceptIfRecipientDomainIs" $MalwareFilterRule.ExceptIfRecipientDomainIs
        $MalwareFilterRuleCmdlet += makeparam "ExceptIfSentTo" $MalwareFilterRule.ExceptIfSentTo
        $MalwareFilterRuleCmdlet += makeparam "ExceptIfSentToMemberOf" $MalwareFilterRule.ExceptIfSentToMemberOf
        $MalwareFilterRuleCmdlet += makeparam "RecipientDomainIs" $MalwareFilterRule.RecipientDomainIs
        $MalwareFilterRuleCmdlet += makeparam "SentTo" $MalwareFilterRule.SentTo
        $MalwareFilterRuleCmdlet += makeparam "SentToMemberOf" $MalwareFilterRule.SentToMemberOf
        Add-Content $outfile "`n$MalwareFilterRuleCmdlet"
    }
 }else{
    Write-Host "No Malware Filter Rules to add."
 }
#****************************************************************************
# InboundConnectors
#****************************************************************************
$InboundConnectors = Import-Clixml ".\InboundConnector.xml"
$InboundConnectorCount = $InboundConnectors.Name.Count
if($InboundConnectorCount -gt 0){
    Write-Host "Importing $InboundConnectorCount Inbound Connectors"
    ForEach ($InboundConnector in $InboundConnectors) {
        $InboundConnectorCmdlet = "New-InboundConnector"
        $InboundConnectorCmdlet += makeparam "Name" $InboundConnector.Name
        $InboundConnectorCmdlet += makeparam "SenderDomains" $InboundConnector.SenderDomains

        If($InboundConnector.AssociatedAcceptedDomains.Count -gt 0) {
            If($InboundConnector.AssociatedAcceptedDomains[0].Contains("/")) {
                # This connector was created in an EOP Standard tenant
                # Strip out just the domain name
                $InboundConnectorCmdlet += " -AssociatedAcceptedDomains "
                ForEach  ($accepteddomain in $InboundConnectors.AssociatedAcceptedDomains) {
                    $accepteddomain = $accepteddomain.SubString($accepteddomain.LastIndexOf("/")+1)
                    $InboundConnectorCmdlet += "`"$accepteddomain`","
                }
                $InboundConnectorCmdlet = $InboundConnectorCmdlet.TrimEnd(",")
            }else{
                $InboundConnectorCmdlet += makeparam "AssociatedAcceptedDomains" $InboundConnector.AssociatedAcceptedDomains
            }
        }

        $InboundConnectorCmdlet += makeparam "CloudServicesMailEnabled" $InboundConnector.CloudServicesMailEnabled
        $InboundConnectorCmdlet += makeparam "Comment" $InboundConnector.Comment
        $InboundConnectorCmdlet += " -Confirm:`$False"
        $InboundConnectorCmdlet += makeparam "ConnectorSource" $InboundConnector.ConnectorSource
        $InboundConnectorCmdlet += makeparam "ConnectorType" $InboundConnector.ConnectorType
        $InboundConnectorCmdlet += makeparam "Enabled" $InboundConnector.Enabled
        $InboundConnectorCmdlet += makeparam "RequireTls" $InboundConnector.RequireTls
        $InboundConnectorCmdlet += makeparam "RestrictDomainsToCertificate" $InboundConnector.RestrictDomainsToCertificate
        $InboundConnectorCmdlet += makeparam "RestrictDomainsToIPAddresses" $InboundConnector.RestrictDomainsToIPAddresses
        $InboundConnectorCmdlet += makeparam "SenderIPAddresses" $InboundConnector.SenderIPAddresses
        $InboundConnectorCmdlet += makeparam "TlsSenderCertificateName" $InboundConnector.TlsSenderCertificateName
        Add-Content $outfile "`n$InboundConnectorCmdlet"
     }
}else{
    Write-Host "No Inbound Connectors to add."
 }
#****************************************************************************
# OutboundConnector
#****************************************************************************
$OutboundConnectors = Import-Clixml ".\OutboundConnector.xml"
$OutboundConnectorCount = $OutboundConnectors.Name.Count
if($OutboundConnectorCount -gt 0){
    Write-Host "Importing $OutboundConnectorCount Outbound Connectors"
    ForEach ($OutboundConnector in $OutboundConnectors) {
        $OutboundConnectorCmdlet = "New-OutboundConnector"
        $OutboundConnectorCmdlet += makeparam "Name" $OutboundConnector.Name
        $OutboundConnectorCmdlet += makeparam "AllAcceptedDomains" $OutboundConnector.AllAcceptedDomains
        $OutboundConnectorCmdlet += makeparam "BypassValidation" $OutboundConnector.BypassValidation
        $OutboundConnectorCmdlet += makeparam "CloudServicesMailEnabled" $OutboundConnector.CloudServicesMailEnabled
        $OutboundConnectorCmdlet += makeparam "Comment" $OutboundConnector.Comment
        $OutboundConnectorCmdlet += " -Confirm:`$False"
        $OutboundConnectorCmdlet += makeparam "ConnectorSource" $OutboundConnector.ConnectorSource
        $OutboundConnectorCmdlet += makeparam "ConnectorType" $OutboundConnector.ConnectorType
        $OutboundConnectorCmdlet += makeparam "IsTransportRuleScoped" $OutboundConnector.IsTransportRuleScoped
        $OutboundConnectorCmdlet += makeparam "RecipientDomains" $OutboundConnector.RecipientDomains
        $OutboundConnectorCmdlet += makeparam "RouteAllMessagesViaOnPremises" $OutboundConnector.RouteAllMessagesViaOnPremises
        $OutboundConnectorCmdlet += makeparam "SmartHosts" $OutboundConnector.SmartHosts
        $OutboundConnectorCmdlet += makeparam "TlsDomain" $OutboundConnector.TlsDomain
        $OutboundConnectorCmdlet += makeparam "TlsSettings" $OutboundConnector.TlsSettings
        $OutboundConnectorCmdlet += makeparam "UseMXRecord" $OutboundConnector.UseMXRecord
        Add-Content $outfile "`n$OutboundConnectorCmdlet"
    }
 }else{
    Write-Host "No Outbound Connectors to add."
 }
#*****************************************************************************
# TransportRule
#*****************************************************************************
Add-Content $outfile "`n[Byte[]]$Data = Get-Content -Path `".TransportRules.xml`" -Encoding Byte -ReadCount 0"
Add-Content $outfile "`nImport-TransportRuleCollection -FileData $Data"
#****************************************************************************
# Domain Type
#****************************************************************************
$Domains = Import-Clixml ".\Domains.xml"
$DomainCount = $Domains.Name.Count
if($HostedContentFilterPolicyCount -gt 0){
    Write-Host "Importing $DomainCount Domains"
    ForEach ($Domain in $Domains) {
        $DomainCmdlet = "Set-AcceptedDomain"
        $DomainCmdlet += makeparam "Identity" $Domain.Name
        $DomainCmdlet += makeparam "DomainType" $Domain.DomainType
        Add-Content $outfile "`n$DomainCmdlet"
    }
 }else{
    Write-Host "No Domains to add."
 }
```

## <a name="step-8-revert-your-dns-settings-to-stop-mail-queuing"></a><span data-ttu-id="ac746-184">8단계: 메일 큐를 중지하도록 DNS 설정 되돌리기</span><span class="sxs-lookup"><span data-stu-id="ac746-184">Step 8: Revert your DNS settings to stop mail queuing</span></span>

<span data-ttu-id="ac746-185">MX 레코드를 잘못된 주소로 설정하여 전환하는 동안 보낸 사람이 메일을 큐에 들이게 한 경우 관리 센터에 지정된 올바른 값으로 다시 [설정해야 합니다.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="ac746-185">If you chose to set your MX records to an invalid address to cause the senders to queue mail during your transition, you'll need to set them back to the correct value as specified in the [admin center](https://admin.microsoft.com).</span></span> <span data-ttu-id="ac746-186">DNS 구성에 대한 자세한 내용은 모든 DNS 호스팅 공급자에서 [Microsoft 365용 DNS 레코드 만들기를 참조하세요.](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)</span><span class="sxs-lookup"><span data-stu-id="ac746-186">For more information about configuring DNS, see [Create DNS records at any DNS hosting provider for Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider).</span></span>
