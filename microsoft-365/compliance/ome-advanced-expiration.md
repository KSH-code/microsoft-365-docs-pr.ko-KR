---
title: Office 365 고급 메시지 암호화로 암호화 된 전자 메일의 만료 날짜 설정
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 10/8/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
description: Office 365 Advanced Message Encryption을 사용 하 여 사용자 지정 브랜드 서식 파일을 통해 전자 메일에 만료 날짜를 설정 하 여 이메일 보안을 확장할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e929ce1d948a83a98cca6fa35a65b80a2fc9ef15
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818691"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="c15c0-103">Office 365 고급 메시지 암호화로 암호화 된 전자 메일의 만료 날짜 설정</span><span class="sxs-lookup"><span data-stu-id="c15c0-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="c15c0-104">Office 365 Advanced Message Encryption은 [microsoft 365 Enterprise e5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (비영리 스태프 가격), Office 365 Enterprise E5 (비영리 스태프 가격) 및 Office 365 교육용 A5에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15c0-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="c15c0-105">조직에서 Office 365 고급 메시지 암호화를 포함 하지 않는 구독을 사용 하는 경우 microsoft 365 E3, microsoft 365 E3 (비영리 직원 가격) 또는 Microsoft 365 (고급 규정 준수) 용 microsoft 365 e3, Microsoft 365 E3 (비영리 스태프 가격) 또는 Office 365 Sku에 대 한 Office 준수 sku 추가 기능을 사용해 서 구매할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15c0-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="c15c0-106">사용자가 OME 포털을 사용 하 여 암호화 된 전자 메일에 액세스 하는 외부의 받는 사람에 게 보내는 전자 메일에 메시지 만료를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15c0-106">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="c15c0-107">Windows Powershell에서 만료 날짜를 지정 하는 사용자 지정 브랜드 서식 파일을 사용 하 여 조직에서 보낸 암호화 된 전자 메일을 보고 회신할 때 받는 사람이 OME 포털을 사용 하도록 강제 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15c0-107">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows Powershell.</span></span>

<span data-ttu-id="c15c0-108">O365 전역 관리자는 회사 브랜드를 적용 하 여 조직의 전자 메일 메시지 모양을 사용자 지정할 때 이러한 전자 메일 메시지에 대 한 만료를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15c0-108">As an O365 global administrator, when you apply your company brand to customize the look of your organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="c15c0-109">Office 365 고급 메시지 암호화를 사용 하면 조직에서 보낸 암호화 된 전자 메일용 템플릿을 여러 개 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15c0-109">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="c15c0-110">서식 파일을 사용 하면 받는 사람에 게 사용자가 보낸 메일에 대 한 액세스 권한이 있는 기간을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15c0-110">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="c15c0-111">최종 사용자가 만료 날짜가 설정 된 메일을 받는 경우 사용자는 래퍼 전자 메일에서 만료 날짜를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15c0-111">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="c15c0-112">사용자가 만료 된 메일을 열려고 하면 OME 포털에 오류가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c15c0-112">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="c15c0-113">전자 메일에 대 한 만료 날짜만 외부 받는 사람으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15c0-113">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="c15c0-114">Office 365 고급 메시지 암호화를 사용 하 여 사용자 지정 브랜딩을 적용할 때마다 Office 365에서 해당 래퍼를 서식 파일을 적용 하는 메일 흐름 규칙에 맞는 전자 메일에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15c0-114">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="c15c0-115">또한 사용자 지정 브랜딩을 사용 하는 경우에만 만료를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15c0-115">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="c15c0-116">PowerShell을 사용 하 여 메일 만료를 적용 하는 사용자 지정 브랜딩 서식 파일 만들기</span><span class="sxs-lookup"><span data-stu-id="c15c0-116">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="c15c0-117">조직에서 전역 관리자 권한이 있는 계정을 사용 하 여 [Exchange Online PowerShell에 연결](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15c0-117">[Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your organization.</span></span>

2. <span data-ttu-id="c15c0-118">Set-omeconfiguration cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15c0-118">Run the New-OMEConfiguration cmdlet.</span></span>

     ```powershell
     New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
     ```

<span data-ttu-id="c15c0-119">여기서,</span><span class="sxs-lookup"><span data-stu-id="c15c0-119">Where:</span></span>

- <span data-ttu-id="c15c0-120">`Identity`은 사용자 지정 서식 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="c15c0-120">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="c15c0-121">`ExternalMailExpiryInDays`받는 사람이 만료 되기 전에 메일을 보관할 수 있는 기간 (일)을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="c15c0-121">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="c15c0-122">1 – 730 일 사이에 임의의 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c15c0-122">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="c15c0-123">Office 365 고급 메시지 암호화에 대 한 추가 정보</span><span class="sxs-lookup"><span data-stu-id="c15c0-123">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="c15c0-124">Office 365 고급 메시지 암호화</span><span class="sxs-lookup"><span data-stu-id="c15c0-124">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="c15c0-125">Office 365 고급 메시지 암호화로 암호화된 전자 메일 취소</span><span class="sxs-lookup"><span data-stu-id="c15c0-125">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="c15c0-126">메시지 정책 및 규정 준수 서비스 설명</span><span class="sxs-lookup"><span data-stu-id="c15c0-126">Message policy and compliance service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)
