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
description: '요약: Microsoft Office 365의 데이터 복구 기능을 이해 합니다.'
ms.openlocfilehash: e69d35f08070e1fe092ca8a9b4aef6d179711121
ms.sourcegitcommit: f80c6c52e5b08290f74baec1d64c4070046c32e4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/12/2020
ms.locfileid: "44717349"
---
# <a name="service-encryption"></a><span data-ttu-id="b6637-103">서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="b6637-103">Service Encryption</span></span>

<span data-ttu-id="b6637-104">볼륨 수준 암호화, Exchange Online, 비즈니스용 Skype, SharePoint Online 및 비즈니스용 OneDrive를 사용 하는 것 외에도 서비스 암호화를 사용 하 여 고객 데이터를 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="b6637-105">서비스 암호화를 사용 하면 다음과 같은 두 가지 주요 관리 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-105">Service Encryption allows for two key management options:</span></span>

## <a name="microsoft-managed-keys"></a><span data-ttu-id="b6637-106">Microsoft 관리 키:</span><span class="sxs-lookup"><span data-stu-id="b6637-106">Microsoft managed keys:</span></span> 
<span data-ttu-id="b6637-107">Microsoft는 서비스 암호화를 위한 루트 키를 포함 하 여 모든 암호화 키를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-107">Microsoft manages all cryptographic keys including the root keys for service encryption.</span></span> <span data-ttu-id="b6637-108">이 옵션은 현재 SharePoint Online 및 비즈니스용 OneDrive에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-108">This option is currently available in SharePoint Online and OneDrive for Business.</span></span> <span data-ttu-id="b6637-109">이 옵션은 현재 Exchange Online에 대해 롤아웃 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-109">This option is currently being rolled out for Exchange Online.</span></span> <span data-ttu-id="b6637-110">Microsoft 관리 키는 고객 키를 사용 하 여 온보드를 결정 하지 않은 경우 기본 서비스 암호화를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-110">Microsoft managed keys provide default service encryption unless you decide to onboard using Customer Key.</span></span> <span data-ttu-id="b6637-111">나중에 데이터 제거 경로를 팔 로우 하지 않고 고객 키를 사용 하지 않도록 결정 한 경우 Microsoft 관리 되는 키를 사용 하 여 사용자의 데이터 암호화가 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-111">If, at a later date, you decide to stop using Customer Key without following the data purge path, then your data stays encrypted using the Microsoft managed keys.</span></span> <span data-ttu-id="b6637-112">데이터는 최소한이 기본 수준에서 항상 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-112">Your data is always encrypted at this default level at a minimum.</span></span> 

## <a name="customer-key"></a><span data-ttu-id="b6637-113">고객 키:</span><span class="sxs-lookup"><span data-stu-id="b6637-113">Customer Key:</span></span> 
<span data-ttu-id="b6637-114">서비스 암호화에 사용 되는 루트 키를 제공 하 고 Azure 키 자격 증명 모음을 사용 하 여 이러한 키를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-114">You supply root keys used with service encryption and you manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="b6637-115">Microsoft는 다른 모든 키를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-115">Microsoft manages all other keys.</span></span> <span data-ttu-id="b6637-116">이 옵션은 고객 키 라고 하며, 현재 Exchange Online, SharePoint Online 및 비즈니스용 OneDrive에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-116">This option is called Customer Key, and it is currently available for Exchange Online, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="b6637-117">이전에는 고급 암호화 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-117">(Previously referred to as Advanced Encryption with BYOK.</span></span> <span data-ttu-id="b6637-118">원래 공지 사항을 보려면 [Office 365 고객을 위해 투명도 및 컨트롤 향상](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b6637-118">See [Enhancing transparency and control for Office 365 customers](https://blogs.office.com/2015/04/21/enhancing-transparency-and-control-for-office-365-customers/) for the original announcement.)</span></span>

<span data-ttu-id="b6637-119">서비스 암호화는 여러 가지 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-119">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="b6637-120">예를 들면 고객 키:</span><span class="sxs-lookup"><span data-stu-id="b6637-120">For example, Customer Key:</span></span>

- <span data-ttu-id="b6637-121">강력한 암호화 보호에 대 한 권한 보호 및 관리 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-121">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="b6637-122">다중 테 넌 트 서비스가 테 넌 트 기준 키 관리를 제공할 수 있도록 하는 고객 키 옵션이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-122">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="b6637-123">Windows 운영 체제 관리자가 운영 체제에 의해 저장 되거나 처리 되는 고객 데이터에 대 한 액세스와의 분리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-123">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="b6637-124">암호화에 대 한 준수 요구 사항이 있는 고객의 요구 사항을 충족 하기 위해 Microsoft 365의 기능을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-124">Enhances the ability of Microsoft 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

<span data-ttu-id="b6637-125">고객 키를 사용 하 여 온-프레미스 HSM (하드웨어 서비스 모듈) 또는 AKV (Azure Key Vault)를 사용 하 여 자체 암호화 키를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-125">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="b6637-126">키를 생성 하는 방법에 관계 없이 AKV을 사용 하 여 Office 365에서 사용 하는 암호화 키를 제어 하 고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-126">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="b6637-127">키가 AKV에 저장 되 면 사서함 데이터 나 파일을 암호화 하는 keychains 중 하나의 루트로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-127">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="b6637-128">고객 키의 또 다른 이점은 Microsoft에서 데이터를 처리 하는 기능을 제어 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-128">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="b6637-129">Microsoft에 대 한 서비스를 종료 하거나 클라우드에 저장 된 데이터 부분을 제거 하려는 경우와 같이 Office 365에서 데이터를 제거 하려는 경우에는이 작업을 수행 하 고 고객 키를 기술 컨트롤로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-129">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="b6637-130">이렇게 하면 Microsoft를 비롯 한 아무도 데이터에 액세스 하거나 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-130">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="b6637-131">고객 키는 Microsoft 담당자가 데이터에 대 한 액세스를 제어 하는 데 사용 하는 고객 Lockbox와 보조로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6637-131">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="b6637-132">Exchange Online, 비즈니스용 Skype, SharePoint Online, 팀 사이트 및 비즈니스용 OneDrive에 대해 Microsoft 365에 대 한 고객 키를 설정 하는 방법에 대 한 자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b6637-132">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="b6637-133">고객 키를 사용한 서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="b6637-133">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="b6637-134">고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="b6637-134">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="b6637-135">고객 키 관리</span><span class="sxs-lookup"><span data-stu-id="b6637-135">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="b6637-136">고객 키 또는 가용성 키 롤 또는 회전</span><span class="sxs-lookup"><span data-stu-id="b6637-136">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="b6637-137">가용성 키 이해</span><span class="sxs-lookup"><span data-stu-id="b6637-137">Understand the availability key</span></span>](customer-key-availability-key-understand.md)

