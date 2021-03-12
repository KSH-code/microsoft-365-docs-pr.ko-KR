---
title: Office 365 메시지 암호화를 사용하여 중요한 정보 유형 정책 만들기
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 8/28/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- Strat_O365_Enterprise
description: Office 365 메시지 암호화를 사용하여 조직에 대한 중요한 정보 유형 정책을 만드는 방법을 학습합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 22aec87b149c58b2537f6921fb7c37552ef72f98
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741381"
---
# <a name="create-a-sensitive-information-type-policy-for-your-organization-using-message-encryption"></a><span data-ttu-id="83006-103">메시지 암호화를 사용하여 조직에 대한 중요한 정보 유형 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="83006-103">Create a sensitive information type policy for your organization using Message Encryption</span></span>

<span data-ttu-id="83006-104">Exchange 메일 흐름 규칙 또는 DLP(데이터 손실 방지)를 사용하여 Office 365 메시지 암호화를 사용하여 중요한 정보 유형 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83006-104">You can use either Exchange mail flow rules or Data Loss Prevention (DLP) to create a sensitive information type policy with Office 365 Message Encryption.</span></span> <span data-ttu-id="83006-105">Exchange 메일 흐름 규칙을 만들하려면 EAC(Exchange 관리 센터) 또는 PowerShell을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83006-105">To create an Exchange mail flow rule, you can use either the Exchange admin center (EAC) or PowerShell.</span></span>

## <a name="to-create-the-policy-by-using-mail-flow-rules-in-the-eac"></a><span data-ttu-id="83006-106">EAC에서 메일 흐름 규칙을 사용하여 정책을 만들면</span><span class="sxs-lookup"><span data-stu-id="83006-106">To create the policy by using mail flow rules in the EAC</span></span>

<span data-ttu-id="83006-107">EAC(Exchange 관리 센터)에 로그인하고 메일 흐름 **규칙으로**  >  **이동하세요.**</span><span class="sxs-lookup"><span data-stu-id="83006-107">Sign in to the Exchange admin center (EAC) and go to **Mail flow** > **Rules**.</span></span> <span data-ttu-id="83006-108">규칙 페이지에서 Office 365 메시지 암호화를 적용하는 규칙을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="83006-108">On the Rules page, create a rule that applies Office 365 Message Encryption.</span></span> <span data-ttu-id="83006-109">메시지 또는 첨부 파일에 특정 키워드 또는 중요한 정보 유형이 있는 경우와 같은 조건에 따라 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83006-109">You can create a rule based on conditions such as the presence of certain keywords or sensitive information types in the message or attachment.</span></span>

### <a name="to-create-the-policy-by-using-mail-flow-rules-in-powershell"></a><span data-ttu-id="83006-110">PowerShell에서 메일 흐름 규칙을 사용하여 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83006-110">To create the policy by using mail flow rules in PowerShell</span></span>

<span data-ttu-id="83006-111">조직에서 전역 관리자 권한이 있는 직장 또는 학교 계정을 사용하여 Windows PowerShell 세션을 시작하고 Exchange Online에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="83006-111">Use a work or school account that has global administrator permissions in your organization, start a Windows PowerShell session and connect to Exchange Online.</span></span> <span data-ttu-id="83006-112">지침을 확인하려면 [Exchange Online PowerShell에 연결](https://aka.ms/exopowershell)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="83006-112">For instructions, see [Connect to Exchange Online PowerShell](https://aka.ms/exopowershell).</span></span> <span data-ttu-id="83006-113">정책 Set-IRMConfiguration New-TransportRule cmdlet을 사용하여 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83006-113">Use the Set-IRMConfiguration and New-TransportRule cmdlets to create the policy.</span></span>

## <a name="example-mail-flow-rule-created-with-powershell"></a><span data-ttu-id="83006-114">PowerShell을 통해 만든 메일 흐름 규칙 예</span><span class="sxs-lookup"><span data-stu-id="83006-114">Example mail flow rule created with PowerShell</span></span>

<span data-ttu-id="83006-115">PowerShell에서 다음 명령을 실행하여 전자 메일 또는 첨부 파일에 다음과 같은 중요한 정보 유형이 포함된 경우 암호화 전용 옵션을 사용하여 조직 외부로 전송되는 전자 메일을 자동으로 암호화하는 Exchange 메일 흐름 규칙을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83006-115">Run the following commands in PowerShell to create an Exchange mail flow rule that automatically encrypts emails sent outside your organization with the encrypt-only option if the emails or their attachments contain the following sensitive information types:</span></span>

- <span data-ttu-id="83006-116">ABA 라우팅 번호</span><span class="sxs-lookup"><span data-stu-id="83006-116">ABA routing number</span></span>
- <span data-ttu-id="83006-117">신용 카드 번호</span><span class="sxs-lookup"><span data-stu-id="83006-117">Credit card Number</span></span>
- <span data-ttu-id="83006-118">DEA(마약 집행 기구) 번호</span><span class="sxs-lookup"><span data-stu-id="83006-118">Drug Enforcement Agency (DEA) number</span></span>
- <span data-ttu-id="83006-119">미국/영국</span><span class="sxs-lookup"><span data-stu-id="83006-119">U.S. / U.K.</span></span> <span data-ttu-id="83006-120">passport number</span><span class="sxs-lookup"><span data-stu-id="83006-120">passport number</span></span>
- <span data-ttu-id="83006-121">미국 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="83006-121">U.S. bank account number</span></span>
- <span data-ttu-id="83006-122">미국 ITIN(개인 납세자 번호)</span><span class="sxs-lookup"><span data-stu-id="83006-122">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>
- <span data-ttu-id="83006-123">미국 SSN(사회 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="83006-123">U.S. Social Security Number (SSN)</span></span>

```powershell
Set-IRMConfiguration -DecryptAttachmentForEncryptOnly $true
New-TransportRule -Name "Encrypt outbound sensitive emails (out of box rule)" -SentToScope  NotInOrganization  -ApplyRightsProtectionTemplate "Encrypt" -MessageContainsDataClassifications @(@{Name="ABA Routing Number"; minCount="1"},@{Name="Credit Card Number"; minCount="1"},@{Name="Drug Enforcement Agency (DEA) Number"; minCount="1"},@{Name="U.S. / U.K. Passport Number"; minCount="1"},@{Name="U.S. Bank Account Number"; minCount="1"},@{Name="U.S. Individual Taxpayer Identification Number (ITIN)"; minCount="1"},@{Name="U.S. Social Security Number (SSN)"; minCount="1"}) -SenderNotificationType "NotifyOnly"
```

<span data-ttu-id="83006-124">자세한 내용은 [Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration) 및 [New-TransportRule을 참조하세요.](https://docs.microsoft.com/powershell/module/exchange/new-transportrule)</span><span class="sxs-lookup"><span data-stu-id="83006-124">For more information, see [Set-IRMConfiguration](https://docs.microsoft.com/powershell/module/exchange/set-irmconfiguration) and [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/new-transportrule).</span></span>

## <a name="how-recipients-access-attachments"></a><span data-ttu-id="83006-125">받는 사람이 첨부 파일에 액세스하는 방법</span><span class="sxs-lookup"><span data-stu-id="83006-125">How recipients access attachments</span></span>

<span data-ttu-id="83006-126">Microsoft에서 메시지를 암호화한 후 받는 사람은 암호화된 전자 메일에 액세스하고 열 때 첨부 파일에 무제한으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83006-126">After Microsoft encrypts a message, recipients have unrestricted access to attachments when they access and open their encrypted email.</span></span>

## <a name="to-prepare-for-this-change"></a><span data-ttu-id="83006-127">이 변경을 준비하기 위해</span><span class="sxs-lookup"><span data-stu-id="83006-127">To prepare for this change</span></span>

<span data-ttu-id="83006-128">해당 최종 사용자 설명서 및 교육 자료를 업데이트하여 조직의 사용자가 이 변경에 대비할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83006-128">You may want to update any applicable end-user documentation and training materials to prepare people in your organization for this change.</span></span> <span data-ttu-id="83006-129">이러한 Office 365 메시지 암호화 리소스를 사용자와 적절하게 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="83006-129">Share these Office 365 Message Encryption resources with your users as appropriate:</span></span>

- [<span data-ttu-id="83006-130">PC용 Outlook에서 암호화된 메시지 보내기, 보기 및 회신</span><span class="sxs-lookup"><span data-stu-id="83006-130">Send, view, and reply to encrypted messages in Outlook for PC</span></span>](https://support.microsoft.com/en-us/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)
- [<span data-ttu-id="83006-131">Microsoft 365 Essentials 비디오: Office 메시지 암호화</span><span class="sxs-lookup"><span data-stu-id="83006-131">Microsoft 365 Essentials Video: Office Message Encryption</span></span>](https://youtu.be/CQR0cG_iEUc)

## <a name="view-these-changes-in-the-audit-log"></a><span data-ttu-id="83006-132">감사 로그에서 이러한 변경 내용 보기</span><span class="sxs-lookup"><span data-stu-id="83006-132">View these changes in the audit log</span></span>

<span data-ttu-id="83006-133">Microsoft 365는 이 활동을 감사하고 관리자가 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="83006-133">Microsoft 365 audits this activity and makes it available to administrators.</span></span> <span data-ttu-id="83006-134">이 작업은 'New-TransportRule'이고, 보안 및 준수 센터의 감사 로그 검색에서 샘플 감사 & 코드는 아래와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="83006-134">The operation is 'New-TransportRule' and a snippet of a sample audit entry from the Audit Log Search in Security & Compliance Center is below:</span></span>

```text
*{"CreationTime":"2018-11-28T23:35:01","Id":"a1b2c3d4-daa0-4c4f-a019-03a1234a1b0c","Operation":"New-TransportRule","OrganizationId":"123456-221d-12345 ","RecordType":1,"ResultStatus":"True","UserKey":"Microsoft Operator","UserType":3,"Version":1,"Workload":"Exchange","ClientIP":"123.456.147.68:17584","ObjectId":"","UserId":"Microsoft Operator","ExternalAccess":true,"OrganizationName":"contoso.onmicrosoft.com","OriginatingServer":"CY4PR13MBXXXX (15.20.1382.008)","Parameters": {"Name":"Organization","Value":"123456-221d-12346"{"Name":"ApplyRightsProtectionTemplate","Value":"Encrypt"},{"Name":"Name","Value":"Encrypt outbound sensitive emails (out of box rule)"},{"Name":"MessageContainsDataClassifications"…etc.*
```

## <a name="to-disable-or-customize-the-sensitive-information-types-policy"></a><span data-ttu-id="83006-135">중요한 정보 유형 정책을 사용하지 않도록 설정하거나 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="83006-135">To disable or customize the sensitive information types policy</span></span>

<span data-ttu-id="83006-136">Exchange 메일 흐름 규칙을 만든 후 [](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule)   >   EAC(Exchange 관리 센터)의 메일 흐름 규칙으로 이동하여 규칙을 사용하지 않도록 설정하거나 편집하고 "아웃바운드 중요한 전자 메일 *암호화(기본* 규칙 외) " 규칙을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83006-136">Once you've created the Exchange mail flow rule, you can [disable or edit the rule](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules#enable-or-disable-a-mail-flow-rule) by going to **Mail flow** > **Rules** in the Exchange admin center (EAC) and disable the rule "*Encrypt outbound sensitive emails (out of box rule)*".</span></span>
