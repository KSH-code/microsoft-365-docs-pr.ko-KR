---
title: Office 365 고급 메시지 암호화
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 10/8/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: Advanced Message Encryption in Office 365에서는 조직이 만료 되어 Office 365 웹 포털을 통해 암호화 된 전자 메일에 액세스할 수 있도록 하는 방식으로 관리자의 준수 의무를 충족할 수 있습니다.
ms.openlocfilehash: eb6e95b1cbf24ab19df6a595c34721c84c831211
ms.sourcegitcommit: 27a7a373ca77375fdab0690a899135fad16c3cf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2019
ms.locfileid: "37435512"
---
# <a name="office-365-advanced-message-encryption"></a><span data-ttu-id="8e055-103">Office 365 고급 메시지 암호화</span><span class="sxs-lookup"><span data-stu-id="8e055-103">Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="8e055-104">Office 365 Advanced Message Encryption은 [microsoft 365 Enterprise e5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (비영리 스태프 가격), Office 365 Enterprise E5 (비영리 스태프 가격) 및 Office 365 교육용 A5에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e055-104">Office 365 Advanced Message Encryption is included in [Microsoft 365 Enterprise E5](https://www.microsoft.com/microsoft-365/enterprise/home), Office 365 E5, Microsoft 365 E5 (Nonprofit Staff Pricing), Office 365 Enterprise E5 (Nonprofit Staff Pricing), and Office 365 Education A5.</span></span> <span data-ttu-id="8e055-105">조직에서 Office 365 고급 메시지 암호화를 포함 하지 않는 구독을 사용 하는 경우 microsoft 365 E3, Microsoft 365 E3 (비영리 직원 가격) 또는 Office 365 Advanced 용 Microsoft 365 E5 준수 SKU 추가 기능을 통해 구매할 수 있습니다. Microsoft 365 E3, Microsoft 365 E3 (비영리 직원 가격) 또는 Office 365 Sku에 대 한 준수 SKU 추가 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="8e055-105">If your organization has a subscription that does not include Office 365 Advanced Message Encryption, you can purchase it with the Microsoft 365 E5 Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or the Office 365 Advanced Compliance SKU add-on for Microsoft 365 E3, Microsoft 365 E3 (Nonprofit Staff Pricing), or Office 365 SKUs.</span></span>

<span data-ttu-id="8e055-106">Advanced Message Encryption in Office 365에서는 고객이 외부 받는 사람에 대 한 보다 유연한 제어 및 암호화 된 전자 메일 액세스를 필요로 하는 규정 준수 의무를 충족 하도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e055-106">Advanced Message Encryption in Office 365 helps customers meet compliance obligations that require more flexible controls over external recipients and their access to encrypted emails.</span></span> <span data-ttu-id="8e055-107">Office 365의 고급 메시지 암호화를 사용 하 여 조직 외부에서 공유 되는 중요 한 전자 메일을 자동 정책으로 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e055-107">With Advanced Message Encryption in Office 365, you can control sensitive emails shared outside the organization with automatic policies.</span></span> <span data-ttu-id="8e055-108">이러한 정책을 구성 하 여 PII, 재무 또는 상태 Id와 같은 중요 한 정보 유형을 식별 하거나 키워드를 사용 하 여 보호 기능을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e055-108">You configure these policies to identify sensitive information types such as PII, Financial, or Health IDs, or you can use keywords to enhance protection.</span></span> <span data-ttu-id="8e055-109">정책을 구성한 후에는 사용자 지정 브랜드 전자 메일 서식 파일을 사용 하 여 정책을 변경한 다음 정책에 맞는 전자 메일에 대 한 추가 제어를 위해 만료 날짜를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e055-109">Once you've configured the policies, you pair policies with custom branded email templates and then add an expiration date for extra control of emails that fit the policy.</span></span> <span data-ttu-id="8e055-110">또한 관리자는 언제 든 지 메일에 대 한 액세스를 취소 하 여 보안 웹 포털을 통해 외부에서 액세스 하는 암호화 된 전자 메일을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e055-110">Also, admins can further control encrypted emails accessed externally through a secure web portal by revoking access to the mail at any time.</span></span>

<span data-ttu-id="8e055-111">외부의 받는 사람에 게 전송 되는 전자 메일의 만료 날짜만 취소 하 고 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e055-111">You can only revoke and set an expiration date for emails sent to external recipients.</span></span>

<span data-ttu-id="8e055-112">Office 365 고급 메시지 암호화를 사용 하 여 사용자 지정 브랜딩 템플릿을 적용할 때마다 Office 365에서 템플릿을 적용 한 메일 흐름 규칙에 맞는 전자 메일에 래퍼를 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e055-112">With Office 365 Advanced Message Encryption, anytime you apply a custom branding template, Office 365 applies a wrapper to email that fits the mail flow rule to which you apply the template.</span></span> <span data-ttu-id="8e055-113">사용자가 포털을 통해 받은 메시지에만 메시지를 해지 하 고 만료 날짜를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e055-113">You can only revoke messages and apply expiration dates to messages that users receive through the portal.</span></span> <span data-ttu-id="8e055-114">즉, 사용자 지정 브랜딩 서식 파일이 적용 된 전자 메일입니다.</span><span class="sxs-lookup"><span data-stu-id="8e055-114">In other words, email that has a custom branding template applied.</span></span>

## <a name="get-started-with-office-365-advanced-message-encryption"></a><span data-ttu-id="8e055-115">Office 365 Advanced Message Encryption 시작</span><span class="sxs-lookup"><span data-stu-id="8e055-115">Get started with Office 365 Advanced Message Encryption</span></span>

<span data-ttu-id="8e055-116">다음 항목에서는 고급 메시지 암호화를 설정 하 고 사용 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e055-116">The following topics describe how you set up and use Advanced Message Encryption.</span></span>

<span data-ttu-id="8e055-117">조직에 Office 365 고급 메시지 암호화를 포함 하는 구독이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e055-117">Your organization must have a subscription that includes Office 365 Advanced Message Encryption.</span></span> <span data-ttu-id="8e055-118">지원 되는 구독에 대 한 자세한 내용은 [메시지 정책 및 규정 준수 서비스 설명을](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8e055-118">For detailed information about supported subscriptions, see the [Message policy and compliance service description](https://docs.microsoft.com/en-us/office365/servicedescriptions/exchange-online-service-description/message-policy-and-compliance).</span></span>

<span data-ttu-id="8e055-119">아직 Office 365 메시지 암호화를 설정 하지 않은 경우에는 [새 Office 365 메시지 암호화 기능 설정을](set-up-new-message-encryption-capabilities.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8e055-119">If you do not have Office 365 Message Encryption set up already, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span>

<span data-ttu-id="8e055-120">[Office 365 고급 메시지 암호화로 암호화 된 전자 메일의 만료 날짜를 설정](ome-advanced-expiration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8e055-120">[Set an expiration date for email encrypted by Office 365 Advanced Message Encryption](ome-advanced-expiration.md).</span></span> <span data-ttu-id="8e055-121">조직 외부에서 공유 되는 중요 한 전자 메일 제어 보안 웹 포털을 통해 암호화 된 전자 메일을 통해 액세스를 만료 하는 자동 정책으로 보호를 강화 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e055-121">Control sensitive emails shared outside the organization with automatic policies that enhance protection by expiring access through a secure web portal to encrypted emails.</span></span>

<span data-ttu-id="8e055-122">[Office 365 고급 메시지 암호화로 암호화 된 전자 메일을 해지](revoke-ome-encrypted-mail.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8e055-122">[Revoke email encrypted by Office 365 Advanced Message Encryption](revoke-ome-encrypted-mail.md).</span></span> <span data-ttu-id="8e055-123">조직 외부에서 공유 되는 중요 한 전자 메일 제어 및 보안 웹 포털을 통한 암호화 된 전자 메일에 대 한 액세스를 해지 하 여 보호 기능 향상</span><span class="sxs-lookup"><span data-stu-id="8e055-123">Control sensitive emails shared outside the organization and enhance protection by revoking access through a secure web portal to encrypted emails.</span></span>  
