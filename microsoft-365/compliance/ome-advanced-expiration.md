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
description: 사용자 Office 365 고급 메시지 암호화 템플릿을 통해 전자 메일의 만료 날짜를 설정하여 전자 메일 보안을 확장할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f936ffa62f31e47f51fc1bcb2765195b0ea809af
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927788"
---
# <a name="set-an-expiration-date-for-email-encrypted-by-office-365-advanced-message-encryption"></a><span data-ttu-id="90889-103">Office 365 고급 메시지 암호화로 암호화 된 전자 메일의 만료 날짜 설정</span><span class="sxs-lookup"><span data-stu-id="90889-103">Set an expiration date for email encrypted by Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="90889-104">Office 365 고급 메시지 암호화 [Microsoft 365 Enterprise E5,](https://www.microsoft.com/microsoft-365/enterprise/home)Office 365 E5, Microsoft 365 E5(비영리 직원 가격), Office 365 Enterprise E5(비영리 직원 가격 책정) 및 Office 365 Education A5에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90889-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="90889-105">조직에 Office 365 고급 메시지 암호화 없는 구독이 있는 경우 Microsoft 365 E3, Microsoft 365 E3 Microsoft 365 E5 Compliance(비영리 직원 가격) 또는 Microsoft 365 E3(비영리 직원 가격) 또는 Microsoft 365 E3(비영리 직원 가격) 또는 Office 365 SKU용 Office 365 Advanced Compliance SKU 추가 기능을 사용하여 구입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90889-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="90889-106">사용자가 OME 포털을 사용하여 암호화된 전자 메일에 액세스하는 외부 받는 사람에게 보내는 전자 메일에 메시지 만료를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90889-106">You can use message expiration on emails that your users send to external recipients who use the OME Portal to access encrypted emails.</span></span> <span data-ttu-id="90889-107">받는 사람이 OME 포털을 사용하여 조직의 만료 날짜를 지정하는 사용자 지정 브랜드 템플릿을 사용하여 조직에서 보낸 암호화된 전자 메일을 보고 회신하게 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="90889-107">You force recipients to use the OME portal to view and reply to encrypted emails sent by your organization by using a custom branded template that specifies an expiration date in Windows PowerShell.</span></span>

<span data-ttu-id="90889-108">전역 Office 365 조직의 전자 메일 메시지 모양을 사용자 지정하기 위해 회사 브랜드를 적용할 때 이러한 전자 메일 메시지의 만료를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90889-108">As an Office 365 global administrator, when you apply your company brand to customize the look of your organization's email messages, you can also specify an expiration for these email messages.</span></span> <span data-ttu-id="90889-109">이 Office 365 고급 메시지 암호화 조직에서 전송되는 암호화된 전자 메일에 대해 여러 템플릿을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90889-109">With Office 365 Advanced Message Encryption, you can create multiple templates for encrypted emails that originate from your organization.</span></span> <span data-ttu-id="90889-110">템플릿을 사용하여 받는 사람이 사용자가 보낸 메일에 액세스할 수 있는 기간을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90889-110">Using a template, you can control how long recipients have access to mail sent by your users.</span></span>

<span data-ttu-id="90889-111">최종 사용자가 만료 날짜가 설정된 메일을 받으면 래퍼 전자 메일에 만료 날짜가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="90889-111">When an end user receives mail that has an expiration date set, the user sees the expiration date in the wrapper email.</span></span> <span data-ttu-id="90889-112">사용자가 만료된 메일을 열려고 하는 경우 OME 포털에 오류가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="90889-112">If a user tries to open an expired mail, an error appears in the OME portal.</span></span>

<span data-ttu-id="90889-113">외부 받는 사람에게만 전자 메일의 만료 날짜를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90889-113">You can only set expiration dates for emails to external recipients.</span></span>

<span data-ttu-id="90889-114">사용자 Office 365 고급 메시지 암호화 적용할 때 언제든지 Office 365 서식 파일을 적용하는 메일 흐름 규칙에 맞는 전자 메일에 래퍼를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="90889-114">With Office 365 Advanced Message Encryption, anytime you apply custom branding, the Office 365 applies the wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="90889-115">또한 사용자 지정 브랜드를 사용하는 경우 만료만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90889-115">In addition, you can only use expiration if you use custom branding.</span></span>

## <a name="create-a-custom-branding-template-to-force-mail-expiration-by-using-powershell"></a><span data-ttu-id="90889-116">PowerShell을 사용하여 메일 만료를 강제로 하는 사용자 지정 브랜징 템플릿 만들기</span><span class="sxs-lookup"><span data-stu-id="90889-116">Create a custom branding template to force mail expiration by using PowerShell</span></span>

1. <span data-ttu-id="90889-117">커넥트 전역 Exchange Online 권한이 있는 계정으로 [PowerShell을](/powershell/exchange/connect-to-exchange-online-powershell) 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90889-117">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) with an account that has global administrator permissions in your organization.</span></span>

2. <span data-ttu-id="90889-118">cmdlet을 New-OMEConfiguration 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="90889-118">Run the New-OMEConfiguration cmdlet.</span></span>

    ```powershell
    New-OMEConfiguration -Identity "Expire in 7 days" -ExternalMailExpiryInDays 7
    ```

<span data-ttu-id="90889-119">여기서,</span><span class="sxs-lookup"><span data-stu-id="90889-119">Where:</span></span>

- <span data-ttu-id="90889-120">`Identity` 은 사용자 지정 서식 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="90889-120">`Identity` is the name of the custom template.</span></span>

- <span data-ttu-id="90889-121">`ExternalMailExpiryInDays` 메일이 만료되기 전에 받는 사람이 메일을 유지할 수 있는 기간(일)을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="90889-121">`ExternalMailExpiryInDays` identifies the number of days that recipients can keep mail before it expires.</span></span> <span data-ttu-id="90889-122">1~730일 사이의 값을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="90889-122">You can use any value between 1–730 days.</span></span>

## <a name="more-information-about-office-365-advanced-message-encryption"></a><span data-ttu-id="90889-123">자세한 내용은 Office 365 고급 메시지 암호화</span><span class="sxs-lookup"><span data-stu-id="90889-123">More information about Office 365 Advanced Message Encryption</span></span>

- [<span data-ttu-id="90889-124">Office 365 고급 메시지 암호화</span><span class="sxs-lookup"><span data-stu-id="90889-124">Office 365 Advanced Message Encryption</span></span>](ome-advanced-message-encryption.md)

- [<span data-ttu-id="90889-125">Office 365 고급 메시지 암호화로 암호화된 전자 메일 취소</span><span class="sxs-lookup"><span data-stu-id="90889-125">Revoke email encrypted by Office 365 Advanced Message Encryption</span></span>](revoke-ome-encrypted-mail.md)

- [<span data-ttu-id="90889-126">메시지 정책 및 규정 준수 서비스 설명</span><span class="sxs-lookup"><span data-stu-id="90889-126">Message policy and compliance service description</span></span>](/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)