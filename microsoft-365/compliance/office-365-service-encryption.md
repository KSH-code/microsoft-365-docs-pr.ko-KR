---
title: Office 365 서비스 암호화
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.date: 4/8/2020
localization_priority: None
search.appverid:
- MET150
ms.collection: Strat_O365_Enterprise
description: '요약: Microsoft Office 365의 서비스 계층에서 데이터 암호화를 이해 합니다.'
ms.openlocfilehash: a8faded033ade013924eeeab269aa213840430b4
ms.sourcegitcommit: 13f28aa762e467bab8ab1e95e1917b3ac28931da
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2020
ms.locfileid: "43193464"
---
# <a name="office-365-service-encryption"></a><span data-ttu-id="37bb7-103">Office 365 서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="37bb7-103">Office 365 Service Encryption</span></span>

<span data-ttu-id="37bb7-104">볼륨 수준 암호화를 위해 BitLocker를 사용 하는 것 외에도 Exchange Online, 비즈니스용 Skype, SharePoint Online, 비즈니스용 OneDrive 및 팀은 서비스 암호화를 사용 하 여 고객 데이터를 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="37bb7-104">In addition to using BitLocker for volume-level encryption, Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams also use Service Encryption to encrypt customer data.</span></span> <span data-ttu-id="37bb7-105">서비스 암호화를 사용 하면 다음과 같은 두 가지 주요 관리 옵션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37bb7-105">Service Encryption allows for two key management options:</span></span>

- <span data-ttu-id="37bb7-106">Microsoft는 모든 암호화 키를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="37bb7-106">Microsoft manages all cryptographic keys.</span></span> <span data-ttu-id="37bb7-107">이 옵션은 현재 SharePoint Online, 비즈니스용 OneDrive, 비즈니스용 Skype 및 팀 채팅에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37bb7-107">This option is currently available in SharePoint Online, OneDrive for Business, Skype for Business, and Teams chats.</span></span> <span data-ttu-id="37bb7-108">데이터는 기본적으로 Microsoft 관리 되는 키를 사용 하 여 암호화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37bb7-108">Your data is encrypted by default with Microsoft managed keys.</span></span>

- <span data-ttu-id="37bb7-109">조직에서 루트 키를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="37bb7-109">Your organization supplies the root keys.</span></span> <span data-ttu-id="37bb7-110">Azure 키 자격 증명 모음을 사용 하 여 이러한 키를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="37bb7-110">You manage these keys using Azure Key Vault.</span></span> <span data-ttu-id="37bb7-111">이 옵션을 Customer 키 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="37bb7-111">This option is called Customer Key.</span></span> <span data-ttu-id="37bb7-112">현재 Exchange Online, SharePoint Online, 비즈니스용 OneDrive, 비즈니스용 Skype 및 팀 파일에 대해 고객 키를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37bb7-112">Customer Key is currently available for Exchange Online, SharePoint Online, OneDrive for Business, Skype for Business, and Teams files.</span></span> <span data-ttu-id="37bb7-113">고객 키를 사용 하는 경우 이러한 키는 Microsoft 관리 되는 키를 대체 하 여 데이터를 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="37bb7-113">If you use Customer Key, these keys replace Microsoft managed keys to encrypt your data.</span></span>

<span data-ttu-id="37bb7-114">선택한 옵션에 관계 없이 서비스 암호화는 다음과 같은 여러 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="37bb7-114">Regardless of the option you choose, service encryption provides multiple benefits:</span></span>

- <span data-ttu-id="37bb7-115">사용자 인증을 적용 하 여 권한 있는 사용자가 요청한 데이터를 검색 하 고 해독 합니다.</span><span class="sxs-lookup"><span data-stu-id="37bb7-115">Enforces user authentication to retrieve and decrypt data requested by an authorized user.</span></span>

- <span data-ttu-id="37bb7-116">Windows 운영 체제 관리자가 운영 체제에 의해 저장 되거나 처리 되는 고객 데이터에 대 한 액세스와의 분리를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="37bb7-116">Provides separation of Windows operating system administrators from access to customer data stored or processed by the operating system.</span></span>

- <span data-ttu-id="37bb7-117">암호화에 대 한 준수 요구 사항이 있는 고객의 요구 사항을 충족 하기 위해 Office 365의 기능을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="37bb7-117">Enhances the ability of Office 365 to meet the demands of customers that have compliance requirements regarding encryption.</span></span>

<span data-ttu-id="37bb7-118">Exchange Online, 비즈니스용 Skype, SharePoint Online, 비즈니스용 OneDrive 및 팀 파일에 대 한 Office 365의 고객 키를 설정 하는 방법에 대 한 자세한 내용은 다음 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37bb7-118">To learn how to set up Customer Key for Office 365 for Exchange Online, Skype for Business, SharePoint Online, OneDrive for Business, and Teams files, see these articles:</span></span>

- [<span data-ttu-id="37bb7-119">Office 365의 고객 키를 사용한 서비스 암호화</span><span class="sxs-lookup"><span data-stu-id="37bb7-119">Service encryption with Customer Key in Office 365</span></span>](customer-key-overview.md)

- [<span data-ttu-id="37bb7-120">Office 365에 대 한 고객 키 설정</span><span class="sxs-lookup"><span data-stu-id="37bb7-120">Set up Customer Key for Office 365</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="37bb7-121">Office 365에 대 한 고객 키 관리</span><span class="sxs-lookup"><span data-stu-id="37bb7-121">Manage Customer Key for Office 365</span></span>](customer-key-manage.md)

- [<span data-ttu-id="37bb7-122">고객 키 또는 가용성 키 롤 또는 회전</span><span class="sxs-lookup"><span data-stu-id="37bb7-122">Roll or rotate a customer key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="37bb7-123">가용성 키 이해</span><span class="sxs-lookup"><span data-stu-id="37bb7-123">Understand the availability key</span></span>](customer-key-availability-key-understand.md)
