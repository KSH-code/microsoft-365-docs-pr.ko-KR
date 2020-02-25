---
title: 고급 헌팅을 사용하여 다양한 장치와 전자 메일에서 위협을 찾기
description: 장치와 전자 메일을 포괄하는 일반적인 헌팅 시나리오와 예제 쿼리를 연구하세요.
keywords: 고급 헌팅, Office365 데이터, Windows 장치, Office365 전자 메일 표준화, 전자 메일, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석, Microsoft 365, Microsoft Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 0bbcef72fa305819c9f8e0813cfcdfd6c2b0fff3
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/24/2020
ms.locfileid: "42234727"
---
# <a name="hunt-for-threats-across-devices-and-emails"></a><span data-ttu-id="f8b04-104">여러 장치 및 전자 메일에서 위협을 탐지</span><span class="sxs-lookup"><span data-stu-id="f8b04-104">Hunt for threats across devices and emails</span></span>

<span data-ttu-id="f8b04-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f8b04-105">**Applies to:**</span></span>
- <span data-ttu-id="f8b04-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f8b04-106">Microsoft Threat Protection</span></span>



<span data-ttu-id="f8b04-107">Microsoft Threat Protection의 [고급 헌팅](advanced-hunting-overview.md)을 통해 Windows 장치 및 Office 365 전자 메일 전반에 걸쳐 위협을 사전에 헌팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8b04-107">[Advanced hunting](advanced-hunting-overview.md) in Microsoft Threat Protection allows you to proactively hunt for threats across your Windows devices and Office 365 emails.</span></span> <span data-ttu-id="f8b04-108">다음은 장치와 전자 메일을 모두 포괄하는 쿼리를 구성하는 방법을 탐색하는 데 도움이 되는 몇 가지 헌팅 시나리오와 예제 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="f8b04-108">Here are some hunting scenarios and sample queries that can help you explore how you might construct queries covering both devices and emails.</span></span>

## <a name="obtain-user-accounts-from-email-addresses"></a><span data-ttu-id="f8b04-109">전자 메일 주소에서 사용자 계정 가져오기</span><span class="sxs-lookup"><span data-stu-id="f8b04-109">Obtain user accounts from email addresses</span></span>
<span data-ttu-id="f8b04-110">[장치와 전자 메일을 포함하는 테이블](advanced-hunting-schema-tables.md)에서 쿼리를 생성할 때 보낸 사람 또는 받는 사람 전자 메일 주소에서 사용자 계정 이름을 확인해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8b04-110">When constructing queries across [tables that cover devices and emails](advanced-hunting-schema-tables.md), you will likely need to obtain user account names from sender or recipient email addresses.</span></span> <span data-ttu-id="f8b04-111">이렇게 하려면 전자 메일 주소에서 *로컬 호스트*를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f8b04-111">To do this use the *local-host* from the email address:</span></span>

```kusto
AccountName = tostring(split(SenderFromAddress, "@")[0])
```

<span data-ttu-id="f8b04-112">이 정규화 기법은 이후의 시나리오에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8b04-112">This normalization technique is used in the succeeding scenarios.</span></span>

## <a name="hunting-scenarios"></a><span data-ttu-id="f8b04-113">헌팅 시나리오</span><span class="sxs-lookup"><span data-stu-id="f8b04-113">Hunting scenarios</span></span>

### <a name="check-if-files-from-a-known-malicious-sender-are-on-your-devices"></a><span data-ttu-id="f8b04-114">알려진 악의적인 보낸 사람의 파일이 장치에 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="f8b04-114">Check if files from a known malicious sender are on your devices</span></span>
<span data-ttu-id="f8b04-115">악의적인 파일을 보내는 전자 메일 주소를 알고 있다고 가정하고 이 쿼리를 실행하여 이 보낸 사람의 파일이 장치에 존재하는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8b04-115">Assuming you know of an email address sending malicious files, you can run this query to determine if files from this sender exist on your devices.</span></span> <span data-ttu-id="f8b04-116">예를 들어 이 쿼리를 사용하여 맬웨어 배포 캠페인의 영향을 받는 장치 수를 판단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8b04-116">You can use this query, for example, to determine the number of devices affected by a malware distribution campaign.</span></span>

```kusto
//Get prevalence of files sent by a malicious sender in your organization
EmailAttachmentInfo
| where SenderFromAddress =~ "MaliciousSender@example.com"
| where isnotempty(SHA256)
| join (
DeviceFileEvents
| project FileName, SHA256
) on SHA256
```

### <a name="review-logon-attempts-after-receipt-of-malicious-emails"></a><span data-ttu-id="f8b04-117">악의적인 전자 메일을 받은 후에 로그온 시도를 검토합니다.</span><span class="sxs-lookup"><span data-stu-id="f8b04-117">Review logon attempts after receipt of malicious emails</span></span>
<span data-ttu-id="f8b04-118">이 쿼리는 알려진 악의적인 전자 메일을 받은 후 30분 이내에 전자 메일 받는 사람이 수행한 10개의 최신 로그온을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f8b04-118">This query finds the 10 latest logons performed by email recipients within 30 minutes after they received known malicious emails.</span></span> <span data-ttu-id="f8b04-119">이 쿼리를 사용하여 전자 메일 받는 사람의 계정이 노출되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8b04-119">You can use this query to check whether the accounts of the email recipients have been compromised.</span></span>

```kusto
//Find logons that occurred right after malicious email was received
let MaliciousEmail=EmailEvents
| where MalwareFilterVerdict == "Malware" 
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
MaliciousEmail
| join (
DeviceLogonEvents
| project LogonTime = Timestamp, AccountName, DeviceName
) on AccountName 
| where (LogonTime - TimeEmail) between (0min.. 30min)
| take 10
```

### <a name="review-powershell-activities-after-receipt-of-emails-from-known-malicious-sender"></a><span data-ttu-id="f8b04-120">알려진 악의적인 보낸 사람의 전자 메일을 수신 후 PowerShell 활동 검토</span><span class="sxs-lookup"><span data-stu-id="f8b04-120">Review PowerShell activities after receipt of emails from known malicious sender</span></span>
<span data-ttu-id="f8b04-121">악의적인 전자 메일에는 종종 추가 페이로드를 전달하기 위해 PowerShell 명령을 실행하는 문서 및 특수하게 조작된 기타 첨부 파일이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8b04-121">Malicious emails often contain documents and other specially crafted attachments that run PowerShell commands to deliver additional payloads.</span></span> <span data-ttu-id="f8b04-122">악의적인 발신자가 보낸 전자 메일을 알고 있는 경우 이 쿼리를 사용하여 보낸 사람으로부터 전자 메일을 받은 후 30분 이내에 발생한 PowerShell 활동을 나열하고 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f8b04-122">If you are aware of emails coming from a known malicious sender, you can use this query to list and review PowerShell activities that occurred within 30 minutes after an email was received from the sender .</span></span>  

```kusto
//Find PowerShell activities right after email was received from malicious sender
let x=EmailEvents
| where SenderFromAddress =~ "MaliciousSender@example.com"
| project TimeEmail = Timestamp, Subject, SenderFromAddress, AccountName = tostring(split(RecipientEmailAddress, "@")[0]);
x
| join (
DeviceProcessEvents
| where FileName =~ "powershell.exe"
//| where InitiatingProcessParentFileName =~ "outlook.exe"
| project TimeProc = Timestamp, AccountName, DeviceName, InitiatingProcessParentFileName, InitiatingProcessFileName, FileName, ProcessCommandLine
) on AccountName 
| where (TimeProc - TimeEmail) between (0min.. 30min)
```

## <a name="related-topics"></a><span data-ttu-id="f8b04-123">관련 항목</span><span class="sxs-lookup"><span data-stu-id="f8b04-123">Related topics</span></span>
- [<span data-ttu-id="f8b04-124">사전 대응식 위협 탐지</span><span class="sxs-lookup"><span data-stu-id="f8b04-124">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f8b04-125">쿼리 언어 배우기</span><span class="sxs-lookup"><span data-stu-id="f8b04-125">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f8b04-126">공유 쿼리 사용</span><span class="sxs-lookup"><span data-stu-id="f8b04-126">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f8b04-127">스키마의 이해</span><span class="sxs-lookup"><span data-stu-id="f8b04-127">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f8b04-128">쿼리 모범 사례 적용</span><span class="sxs-lookup"><span data-stu-id="f8b04-128">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
