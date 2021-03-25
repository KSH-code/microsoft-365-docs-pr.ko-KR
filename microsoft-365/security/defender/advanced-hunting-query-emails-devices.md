---
title: 고급 헌팅을 사용하여 장치, 전자 메일, 앱 및 ID 전반에 걸쳐 위협을 찾기
description: 장치, 전자 메일, 앱 및 ID를 다루는 일반적인 헌팅 시나리오 및 샘플 쿼리를 연구합니다.
keywords: 고급 헌팅, Office365 데이터, Windows 장치, Office365 전자 메일 정규화, 전자 메일, 앱, ID, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: e494bfe57c31c1d5044f72a8adb3e2548d531604
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199152"
---
# <a name="hunt-for-threats-across-devices-emails-apps-and-identities"></a><span data-ttu-id="4817e-104">장치, 전자 메일, 앱 및 ID에 대한 위협 검색</span><span class="sxs-lookup"><span data-stu-id="4817e-104">Hunt for threats across devices, emails, apps, and identities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="4817e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="4817e-105">**Applies to:**</span></span>
- <span data-ttu-id="4817e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4817e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="4817e-107">[](advanced-hunting-overview.md) Microsoft 365 Defender의 고급 헌팅을 사용하면 다음 전반에 걸쳐 위협을 사전 대응적으로 헌팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender allows you to proactively hunt for threats across:</span></span>
- <span data-ttu-id="4817e-108">끝점용 Microsoft Defender에서 관리하는 장치</span><span class="sxs-lookup"><span data-stu-id="4817e-108">Devices managed by Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="4817e-109">Microsoft 365에서 처리된 전자 메일</span><span class="sxs-lookup"><span data-stu-id="4817e-109">Emails processed by Microsoft 365</span></span>
- <span data-ttu-id="4817e-110">Microsoft Cloud App Security 및 Id에 대한 Microsoft Defender에서 추적하는 클라우드 앱 활동, 인증 이벤트 및 도메인 컨트롤러 활동</span><span class="sxs-lookup"><span data-stu-id="4817e-110">Cloud app activities, authentication events, and domain controller activities tracked by Microsoft Cloud App Security and Microsoft Defender for Identity</span></span>

<span data-ttu-id="4817e-111">이 수준의 가시성을 통해 전자 메일 또는 웹에 도착하는 정교한 침입을 포함하여 네트워크의 섹션을 트래버스하는 위협을 빠르게 찾거나, 로컬 권한을 상승하고, 권한이 부여된 도메인 자격 증명을 획득하고, 장치 전체로 이동하는 위협을 빠르게 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-111">With this level of visibility, you can quickly hunt for threats that traverse sections of your network, including sophisticated intrusions that arrive on email or the web, elevate local privileges, acquire privileged domain credentials, and move laterally to across your devices.</span></span> 

<span data-ttu-id="4817e-112">다음은 이러한 정교한 위협을 헌팅할 때 쿼리를 구성하는 방법을 탐색하는 데 도움이 되는 다양한 헌팅 시나리오를 기반으로 하는 일반적인 기술 및 예제 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-112">Here are general techniques and sample queries based on various hunting scenarios that can help you explore how you might construct queries when hunting for such sophisticated threats.</span></span>

## <a name="get-entity-info"></a><span data-ttu-id="4817e-113">엔터티 정보 보기</span><span class="sxs-lookup"><span data-stu-id="4817e-113">Get entity info</span></span>
<span data-ttu-id="4817e-114">이러한 쿼리를 사용하여 사용자 계정, 장치 및 파일에 대한 정보를 빠르게 얻을 수 있는 방법을 배울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-114">Use these queries to learn how you can quickly get information about user accounts, devices, and files.</span></span> 

### <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="4817e-115">전자 메일 주소에서 사용자 계정 가져오기</span><span class="sxs-lookup"><span data-stu-id="4817e-115">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="4817e-116">[장치와 전자 메일을 포함하는 테이블](advanced-hunting-schema-tables.md)에서 쿼리를 생성할 때 보낸 사람 또는 받는 사람 전자 메일 주소에서 사용자 계정 이름을 확인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-116">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="4817e-117">일반적으로 전자 메일 주소의 *local-host를* 사용하여 받는 사람 또는 보낸 사람 주소에 대해 이 작업을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-117">You can generally do this for either recipient or sender address using the *local-host* from the email address.</span></span>

<span data-ttu-id="4817e-118">아래 스니킷에서 [tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto 함수를 사용하여 열의 받는 사람 전자 메일 주소 바로 앞에 있는 로컬 호스트를 `@` `RecipientEmailAddress` 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-118">In the snippet below, we use the [tostring()](/azure/data-explorer/kusto/query/tostringfunction) Kusto function to extract the local-host right before the `@` from recipient email addresses in the column `RecipientEmailAddress`.</span></span>

```kusto
//Query snippet showing how to extract the account name from an email address
AccountName = tostring(split(RecipientEmailAddress, "@")[0])
```
<span data-ttu-id="4817e-119">아래 쿼리는 이 잘라 내는 방법을 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="4817e-119">The query below shows how this snippet can be used:</span></span>

```kusto
EmailEvents
| where Timestamp > ago(7d)
| project RecipientEmailAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
```

### <a name="merge-the-identityinfo-table"></a><span data-ttu-id="4817e-120">IdentityInfo 테이블 병합</span><span class="sxs-lookup"><span data-stu-id="4817e-120">Merge the IdentityInfo table</span></span>

<span data-ttu-id="4817e-121">[IdentityInfo](advanced-hunting-identityinfo-table.md)테이블을 합치거나 가입하여 계정 이름 및 기타 계정 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-121">You can get account names and other account information by merging or joining the [IdentityInfo table](advanced-hunting-identityinfo-table.md).</span></span> <span data-ttu-id="4817e-122">아래 쿼리는 [EmailEvents](advanced-hunting-emailevents-table.md) 테이블에서 피싱 및 맬웨어 감지 목록을 얻은 다음 해당 정보를 테이블에 조인하여 각 받는 사람에 대한 자세한 `IdentityInfo` 정보를 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-122">The query below obtains the list of phishing and malware detections from the [EmailEvents table](advanced-hunting-emailevents-table.md) and then joins that information with the `IdentityInfo` table to get detailed information about each recipient.</span></span> 

```kusto
EmailEvents
| where Timestamp > ago(7d)
//Get email processing events where the messages were identified as either phishing or malware
| where ThreatTypes has "Malware" or ThreatTypes has "Phish"
//Merge email events with identity info to get recipient details
| join (IdentityInfo | distinct AccountUpn, AccountDisplayName, JobTitle, 
Department, City, Country) on $left.RecipientEmailAddress == $right.AccountUpn 
//Show important message and recipient details
| project Timestamp, NetworkMessageId, Subject, ThreatTypes, 
SenderFromAddress, RecipientEmailAddress, AccountDisplayName, JobTitle, 
Department, City, Country
```

### <a name="get-device-information"></a><span data-ttu-id="4817e-123">장치 정보 얻기</span><span class="sxs-lookup"><span data-stu-id="4817e-123">Get device information</span></span>
<span data-ttu-id="4817e-124">고급 [헌팅 계획은](advanced-hunting-schema-tables.md) 다양한 표에 광범위한 장치 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-124">The [advanced hunting schema](advanced-hunting-schema-tables.md) provides extensive device information in various tables.</span></span> <span data-ttu-id="4817e-125">예를 들어 [DeviceInfo 테이블은](advanced-hunting-deviceinfo-table.md) 정기적으로 집계되는 이벤트 데이터를 기반으로 포괄적인 장치 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-125">For example, the [DeviceInfo table](advanced-hunting-deviceinfo-table.md) provides comprehensive device information based on event data aggregated regularly.</span></span> <span data-ttu-id="4817e-126">이 쿼리는 테이블을 사용하여 잠재적으로 손상된 사용자()가 모든 장치에 로그온한 다음 해당 장치에서 트리거된 경고를 `DeviceInfo` `<account-name>` 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-126">This query uses the `DeviceInfo` table to check if a potentially compromised user (`<account-name>`) has logged on to any devices and then lists the alerts that have been triggered on those devices.</span></span>

>[!Tip]
> <span data-ttu-id="4817e-127">이 쿼리는 내부 조인을 지정하는 데 사용 하여 에 대한 왼쪽 값 중복을 `kind=inner` [](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor) `DeviceId` 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-127">This query uses `kind=inner` to specify an [inner-join](/azure/data-explorer/kusto/query/joinoperator?pivots=azuredataexplorer#inner-join-flavor), which prevents deduplication of left side values for `DeviceId`.</span></span>

```kusto
DeviceInfo
//Query for devices that the potentially compromised account has logged onto
| where LoggedOnUsers contains '<account-name>'
| distinct DeviceId
//Crosscheck devices against alert records in AlertEvidence and AlertInfo tables
| join kind=inner AlertEvidence on DeviceId
| project AlertId
//List all alerts on devices that user has logged on to
| join AlertInfo on AlertId
| project AlertId, Timestamp, Title, Severity, Category 
```

## <a name="hunting-scenarios"></a><span data-ttu-id="4817e-128">헌팅 시나리오</span><span class="sxs-lookup"><span data-stu-id="4817e-128">Hunting scenarios</span></span>

### <a name="list-logon-activities-of-users-that-received-emails-that-were-not-zapped-successfully"></a><span data-ttu-id="4817e-129">잠기지 않은 전자 메일을 받은 사용자의 로그온 활동 나열</span><span class="sxs-lookup"><span data-stu-id="4817e-129">List logon activities of users that received emails that were not zapped successfully</span></span>
<span data-ttu-id="4817e-130">[ZAP(제로](../office-365-security/zero-hour-auto-purge.md) 아워 자동 제거)는 수신된 악성 전자 메일을 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-130">[Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) addresses malicious emails after they have been received.</span></span> <span data-ttu-id="4817e-131">ZAP가 실패하면 결국 디바이스에서 악성 코드가 실행될 수 있으며 계정이 손상된 채로 남을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-131">If ZAP fails, malicious code might eventually run on the device and leave accounts compromised.</span></span> <span data-ttu-id="4817e-132">이 쿼리는 ZAP에서 성공적으로 주소가 제공되지 않은 전자 메일을 받는 사람이 수행한 로그온 활동을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-132">This query checks for logon activity made by the recipients of emails that were not successfully addressed by ZAP.</span></span>

```kusto
EmailPostDeliveryEvents 
| where Timestamp > ago(7d)
//List malicious emails that were not zapped successfully
| where ActionType has "ZAP" and ActionResult == "Error"
| project ZapTime = Timestamp, ActionType, NetworkMessageId , RecipientEmailAddress 
//Get logon activity of recipients using RecipientEmailAddress and AccountUpn
| join kind=inner IdentityLogonEvents on $left.RecipientEmailAddress == $right.AccountUpn
| where Timestamp between ((ZapTime-24h) .. (ZapTime+24h))
//Show only pertinent info, such as account name, the app or service, protocol, the target device, and type of logon
| project ZapTime, ActionType, NetworkMessageId , RecipientEmailAddress, AccountUpn, 
LogonTime = Timestamp, AccountDisplayName, Application, Protocol, DeviceName, LogonType
```

### <a name="get-logon-attempts-by-domain-accounts-targeted-by-credential-theft"></a><span data-ttu-id="4817e-133">자격 증명 도난을 대상으로 하는 도메인 계정으로 로그온 시도하기</span><span class="sxs-lookup"><span data-stu-id="4817e-133">Get logon attempts by domain accounts targeted by credential theft</span></span>
<span data-ttu-id="4817e-134">이 쿼리는 먼저 테이블의 모든 자격 증명 액세스 경고를 `AlertInfo` 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-134">This query first identifies all credential access alerts in the `AlertInfo` table.</span></span> <span data-ttu-id="4817e-135">그런 다음 테이블을 병합하거나 조인하여 대상 계정의 이름과 도메인에 가입된 계정에 대한 필터만 구문 `AlertEvidence` 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-135">It then merges or joins the `AlertEvidence` table, which it parses for the names of the targeted accounts and filters for domain-joined accounts only.</span></span> <span data-ttu-id="4817e-136">마지막으로, 이 테이블을 검사하여 도메인에 가입된 대상 계정의 모든 `IdentityLogonEvents` 로그온 활동을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-136">Finally, it checks the `IdentityLogonEvents` table to get all logon activities by the domain-joined targeted accounts.</span></span>

```kusto
AlertInfo
| where Timestamp > ago(30d)
//Get all credential access alerts
| where Category == "CredentialAccess"
//Get more info from AlertEvidence table to get the SID of the target accounts
| join AlertEvidence on AlertId
| extend IsJoined=(parse_json(AdditionalFields).Account.IsDomainJoined)
| extend TargetAccountSid=tostring(parse_json(AdditionalFields).Account.Sid)
//Filter for domain-joined accounts only
| where IsJoined has "true"
//Merge with IdentityLogonEvents to get all logon attempts by the potentially compromised target accounts
| join kind=inner IdentityLogonEvents on $left.TargetAccountSid == $right.AccountSid
//Show only pertinent info, such as account name, the app or service, protocol, the accessed device, and type of logon
| project AccountDisplayName, TargetAccountSid, Application, Protocol, DeviceName, LogonType
```

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="4817e-137">알려진 악의적인 보낸 사람의 파일이 장치에 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="4817e-137">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="4817e-138">악성 파일을 보내는 전자 메일 주소()를 알고 있는 경우 이 쿼리를 실행하여 이 보낸 사람에 대한 파일이 장치에 있는지 `MaliciousSender@example.com` 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-138">Assuming you know of an email address sending malicious files (`MaliciousSender@example.com`), you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="4817e-139">예를 들어 이 쿼리를 사용하여 맬웨어 배포 캠페인의 영향을 받는 장치를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-139">You can use this query, for example, to identify devices affected by a malware distribution campaign.</span></span>

```kusto
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
//Get emails with attachments identified by a SHA-256
| where isnotempty(SHA256)
| join (
//Check devices for any activity involving the attachments
DeviceFileEvents
| project FileName, SHA256
) on SHA256
| project Timestamp, FileName , SHA256, DeviceName, DeviceId,  NetworkMessageId, SenderFromAddress, RecipientEmailAddress
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="4817e-140">악의적인 전자 메일을 받은 후에 로그온 시도를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-140">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="4817e-141">이 쿼리는 알려진 악의적인 전자 메일을 받은 후 30분 이내에 전자 메일 받는 사람이 수행한 10개의 최신 로그온을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-141">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="4817e-142">이 쿼리를 사용하여 전자 메일 받는 사람의 계정이 노출되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-142">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

```kusto
//Define new table for malicious emails
let MaliciousEmails=EmailEvents
//List emails detected as malware, getting only pertinent columns
| where ThreatTypes has "Malware" 
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmails
| join (
//Merge malicious emails with logon events to find logons by recipients
IdentityLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
//Check only logons within 30 minutes of receipt of an email
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="4817e-143">알려진 악의적인 보낸 사람의 전자 메일을 수신 후 PowerShell 활동 검토</span><span class="sxs-lookup"><span data-stu-id="4817e-143">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="4817e-144">악의적인 전자 메일에는 종종 추가 페이로드를 전달하기 위해 PowerShell 명령을 실행하는 문서 및 특수하게 조작된 기타 첨부 파일이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-144">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="4817e-145">알려진 악의적인 보낸 사람( ) 에서 보낸 전자 메일을 알고 있는 경우 이 쿼리를 사용하여 보낸 사람으로부터 전자 메일을 받은 후 30분 이내에 발생한 PowerShell 활동을 나열하고 검토할 `MaliciousSender@example.com` 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4817e-145">If you are aware of emails coming from a known malicious sender (`MaliciousSender@example.com`), you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender.</span></span>  

```kusto
//Define new table for emails from specific sender
let EmailsFromBadSender=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
//Merge emails from sender with process-related events on devices
EmailsFromBadSender
| join (
DeviceProcessEvents
//Look for PowerShell activity
| where FileName =~ "powershell.exe"
//Add line below to check only events initiated by Outlook
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
//Check only PowerShell activities within 30 minutes of receipt of an email
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a><span data-ttu-id="4817e-146">관련 항목</span><span class="sxs-lookup"><span data-stu-id="4817e-146">Related topics</span></span>
- [<span data-ttu-id="4817e-147">고급 헌팅 개요</span><span class="sxs-lookup"><span data-stu-id="4817e-147">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="4817e-148">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="4817e-148">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="4817e-149">쿼리 결과 작업</span><span class="sxs-lookup"><span data-stu-id="4817e-149">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="4817e-150">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="4817e-150">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="4817e-151">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="4817e-151">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="4817e-152">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="4817e-152">Apply query best practices</span></span>](advanced-hunting-best-practices.md)