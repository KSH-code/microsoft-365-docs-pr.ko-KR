---
title: 서비스 암호화
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 10/3/2019
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '요약: 365에서 데이터 Microsoft Office 이해합니다.'
ms.openlocfilehash: 89f3fbcc90cee0ad822156014ee4ac9e04fe3371
ms.sourcegitcommit: 50f10d83fa21db8572adab90784146e5231e3321
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2021
ms.locfileid: "50058551"
---
# <a name="service-encryption"></a><span data-ttu-id="c1e8f-103">서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="c1e8f-103">Service Encryption</span></span>

<span data-ttu-id="c1e8f-104">볼륨 수준 암호화를 사용하는 것 외에도 Exchange Online, Microsoft Teams, SharePoint Online 및 비즈니스용 OneDrive는 서비스 암호화를 사용하여 고객 데이터를 암호화합니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-104">In addition to using volume-level encryption, Exchange Online, Microsoft Teams, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="c1e8f-105">서비스 암호화를 사용하면 두 가지 주요 관리 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="c1e8f-106">Microsoft에서 관리하는 키</span><span class="sxs-lookup"><span data-stu-id="c1e8f-106">Microsoft-managed keys</span></span>
<span data-ttu-id="c1e8f-107">Microsoft는 서비스 암호화를 위한 루트 키를 포함하여 모든 암호화 키를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="c1e8f-108">이 옵션은 현재 Exchange Online, SharePoint Online, 비즈니스용 OneDrive에 대해 기본적으로 사용하도록 설정되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-108">This option is currently enabled by default for Exchange Online, SharePoint Online, OneDrive for Business.</span></span> <span data-ttu-id="c1e8f-109">고객 키를 사용하여 온보드하기로 결정하지 않은 경우 Microsoft 관리 키는 기본 서비스 암호화를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-109">Microsoft-managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="c1e8f-110">나중에 데이터 제거 경로를 따라가지 않고 고객 키 사용을 중지하기로 결정한 경우 Microsoft에서 관리하는 키를 사용하여 데이터가 암호화된 채로 계속 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-110">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft-managed keys.</span></span> <span data-ttu-id="c1e8f-111">데이터는 최소한 이 기본 수준에서 항상 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-111">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="c1e8f-112">고객 키</span><span class="sxs-lookup"><span data-stu-id="c1e8f-112">Customer Key</span></span>
<span data-ttu-id="c1e8f-113">서비스 암호화에 사용되는 루트 키를 제공하며 Azure Key Vault를 사용하여 이러한 키를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-113">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="c1e8f-114">Microsoft는 다른 모든 키를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-114">Microsoft manages all other keys.</span></span> <span data-ttu-id="c1e8f-115">이 옵션을 고객 키라고 하며 현재 Exchange Online, SharePoint Online 및 비즈니스용 OneDrive에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-115">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="c1e8f-116">(이전에 BYOK를 사용하여 고급 암호화라고 지칭했습니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-116">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="c1e8f-117">원래 [공지에 대한 Office 365](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) 고객에 대한 투명성 및 제어 향상을 참조합니다.)</span><span class="sxs-lookup"><span data-stu-id="c1e8f-117">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="c1e8f-118">서비스 암호화는 여러 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-118">Service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="c1e8f-119">BitLocker 위에 추가된 보호 계층을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-119">Provides an added layer of protection on top of BitLocker.</span></span>

- <span data-ttu-id="c1e8f-120">Windows 운영 체제 관리자가 운영 체제에 의해 저장되거나 처리되는 응용 프로그램 데이터에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-120">Provides separation of Windows operating system administrators from access to application data stored or processed by the operating system.</span></span>

- <span data-ttu-id="c1e8f-121">다중 테넌트 서비스가 테넌트당 키 관리를 제공할 수 있도록 하는 고객 키 옵션을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-121">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="c1e8f-122">암호화와 관련하여 특정 규정 준수 요구 사항이 있는 고객의 요구를 충족하는 Microsoft 365의 기능을 향상합니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-122">Enhances the ability of Microsoft 365 to meet the demands of customers that have specific compliance requirements regarding encryption.</span></span>

<span data-ttu-id="c1e8f-123">고객 키를 사용하면 HSM(하드웨어 서비스 모듈) 또는 AKV(Azure Key Vault)를 사용하여 자체 암호화 키를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-123">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="c1e8f-124">키를 생성하는 방법에 관계없이 AKV를 사용하여 Office 365에서 사용하는 암호화 키를 제어하고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-124">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="c1e8f-125">AKV에 키가 저장되고 나면 사서함 데이터 또는 파일을 암호화하는 키 변경 중 하나의 루트로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-125">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="c1e8f-126">고객 키의 또 다른 이점은 Microsoft가 데이터를 처리하는 기능을 제어할 수 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-126">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="c1e8f-127">Office 365에서 데이터를 제거하려는 경우(예: Microsoft와의 서비스를 종료하거나 클라우드에 저장된 데이터의 일부를 제거하려는 경우) 고객 키를 기술 컨트롤로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-127">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="c1e8f-128">데이터를 제거하면 Microsoft를 비롯한 어느 누구도 데이터에 액세스하거나 데이터를 처리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-128">Removing data ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="c1e8f-129">고객 키는 Microsoft 직원이 데이터에 대한 액세스를 제어하는 데 사용하는 Customer Lockbox에 추가적으로 추가적으로 보완됩니다.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-129">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="c1e8f-130">Exchange Online, Microsoft Teams, SharePoint Online(팀 사이트 및 비즈니스용 OneDrive 포함)에 대한 Microsoft 365 고객 키를 설정하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c1e8f-130">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Microsoft Teams, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="c1e8f-131">고객 키를 사용한 서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="c1e8f-131">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="c1e8f-132">고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="c1e8f-132">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="c1e8f-133">고객 키 관리</span><span class="sxs-lookup"><span data-stu-id="c1e8f-133">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="c1e8f-134">고객 키 또는 가용성 키 롤 또는 회전</span><span class="sxs-lookup"><span data-stu-id="c1e8f-134">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="c1e8f-135">가용성 키 이해</span><span class="sxs-lookup"><span data-stu-id="c1e8f-135">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
