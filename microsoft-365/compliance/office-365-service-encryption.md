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
ms.openlocfilehash: 1c31c0d5524370fd417460fbacf3695df4fa0102
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632243"
---
# <a name="service-encryption"></a><span data-ttu-id="61420-103">서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="61420-103">Service Encryption</span></span>

<span data-ttu-id="61420-104">볼륨 수준 암호화, Exchange Online, 비즈니스용 Skype, SharePoint Online 및 비즈니스용 OneDrive를 사용 하는 것 외에도 서비스 암호화를 사용 하 여 고객 데이터를 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="61420-104">In addition to using volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, and OneDrive for Business also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="61420-105">서비스 암호화를 사용 하면 다음과 같은 두 가지 주요 관리 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61420-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="61420-106">Microsoft는 모든 암호화 키를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="61420-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="61420-107">(이 옵션은 현재 SharePoint Online, 비즈니스용 OneDrive 및 비즈니스용 Skype에서 사용할 수 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="61420-107">(This option is currently available in SharePoint Online, OneDrive for Business, and Skype for Business.)</span></span>

- <span data-ttu-id="61420-108">조직에서 루트 키를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="61420-108">Your organization supplies the root keys.</span></span> <span data-ttu-id="61420-109">Azure 키 자격 증명 모음을 사용 하 여 이러한 키를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="61420-109">You manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="61420-110">이 옵션을 Customer 키 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="61420-110">This option is called Customer Key.</span></span> <span data-ttu-id="61420-111">현재 Exchange Online, SharePoint Online, 비즈니스용 OneDrive, 비즈니스용 Skype 및 팀 파일에 대해 고객 키를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61420-111">Customer Key is currently available for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, and Teams files.</span></span> <span data-ttu-id="61420-112">고객 키를 사용 하는 경우 이러한 키는 Microsoft 관리 되는 키를 대체 하 여 데이터를 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="61420-112">If you use Customer Key, these keys replace Microsoft-managed keys to encrypt your data.</span></span>

<span data-ttu-id="61420-113">서비스 암호화는 여러 가지 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="61420-113">Service encryption provides multiple benefits.</span></span> <span data-ttu-id="61420-114">예를 들면 고객 키:</span><span class="sxs-lookup"><span data-stu-id="61420-114">For example, Customer Key:</span></span>

- <span data-ttu-id="61420-115">강력한 암호화 보호에 대 한 권한 보호 및 관리 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="61420-115">Provides rights protection and management features on top of strong encryption protection.</span></span>

- <span data-ttu-id="61420-116">다중 테 넌 트 서비스가 테 넌 트 기준 키 관리를 제공할 수 있도록 하는 고객 키 옵션이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61420-116">Includes a Customer Key option that enables multi-tenant services to provide per-tenant key management.</span></span>

- <span data-ttu-id="61420-117">Windows 운영 체제 관리자가 운영 체제에 의해 저장 되거나 처리 되는 고객 데이터에 대 한 액세스와의 분리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="61420-117">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="61420-118">암호화에 대 한 준수 요구 사항이 있는 고객의 요구 사항을 충족 하기 위해 Microsoft 365의 기능을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="61420-118">Enhances the ability of Microsoft 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

## <a name="customer-key"></a><span data-ttu-id="61420-119">고객 키</span><span class="sxs-lookup"><span data-stu-id="61420-119">Customer Key</span></span>

<span data-ttu-id="61420-120">고객 키를 사용 하 여 온-프레미스 HSM (하드웨어 서비스 모듈) 또는 AKV (Azure Key Vault)를 사용 하 여 자체 암호화 키를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61420-120">Using Customer Key, you can generate your own cryptographic keys using either an on-premises Hardware Service Module (HSM) or Azure Key Vault (AKV).</span></span> <span data-ttu-id="61420-121">키를 생성 하는 방법에 관계 없이 AKV을 사용 하 여 Office 365에서 사용 하는 암호화 키를 제어 하 고 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="61420-121">Regardless of how you generate the key, you use AKV to control and manage the cryptographic keys used by Office 365.</span></span> <span data-ttu-id="61420-122">키가 AKV에 저장 되 면 사서함 데이터 나 파일을 암호화 하는 keychains 중 하나의 루트로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61420-122">Once your keys are stored in AKV, they can be used as the root of one of the keychains that encrypts your mailbox data or files.</span></span>

<span data-ttu-id="61420-123">고객 키의 또 다른 이점은 Microsoft에서 데이터를 처리 하는 기능을 제어 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="61420-123">Another benefit of Customer Key is the control you have over the ability of Microsoft to process your data.</span></span> <span data-ttu-id="61420-124">Microsoft에 대 한 서비스를 종료 하거나 클라우드에 저장 된 데이터 부분을 제거 하려는 경우와 같이 Office 365에서 데이터를 제거 하려는 경우에는이 작업을 수행 하 고 고객 키를 기술 컨트롤로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="61420-124">If you want to remove data from Office 365, such as if you want to terminate service with Microsoft or remove a portion of your data stored in the cloud, you can do so and use Customer Key as a technical control.</span></span> <span data-ttu-id="61420-125">이렇게 하면 Microsoft를 비롯 한 아무도 데이터에 액세스 하거나 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61420-125">This ensures that no one, including Microsoft, can access or process the data.</span></span> <span data-ttu-id="61420-126">고객 키는 Microsoft 담당자가 데이터에 대 한 액세스를 제어 하는 데 사용 하는 고객 Lockbox와 보조로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61420-126">Customer Key is in addition and complementary to Customer Lockbox that you use to control access to your data by Microsoft personnel.</span></span>

<span data-ttu-id="61420-127">Exchange Online, 비즈니스용 Skype, SharePoint Online, 팀 사이트 및 비즈니스용 OneDrive에 대해 Microsoft 365에 대 한 고객 키를 설정 하는 방법에 대 한 자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="61420-127">To learn how to set up Customer Key for Microsoft 365 for Exchange Online, Skype for Business, SharePoint Online, including Team Sites, and OneDrive for Business, see these articles:</span></span>

- [<span data-ttu-id="61420-128">고객 키를 사용한 서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="61420-128">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="61420-129">고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="61420-129">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="61420-130">고객 키 관리</span><span class="sxs-lookup"><span data-stu-id="61420-130">Manage Customer Key</span></span>](customer-key-manage.md)

- [<span data-ttu-id="61420-131">고객 키 또는 가용성 키 롤 또는 회전</span><span class="sxs-lookup"><span data-stu-id="61420-131">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="61420-132">가용성 키 이해</span><span class="sxs-lookup"><span data-stu-id="61420-132">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
 
