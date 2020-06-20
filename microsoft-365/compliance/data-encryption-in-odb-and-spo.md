---
title: 비즈니스용 OneDrive 및 SharePoint Online에서의 데이터 암호화
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 7/2/2018
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: 비즈니스용 OneDrive 및 SharePoint Online에서 데이터 보안을 위한 암호화의 기본 요소를 이해합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f0c78a9ca6e6bad1e4aea707f8be5dec818b7a27
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817927"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a><span data-ttu-id="81b8f-103">비즈니스용 OneDrive 및 SharePoint Online에서의 데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="81b8f-103">Data Encryption in OneDrive for Business and SharePoint Online</span></span>

<span data-ttu-id="81b8f-104">비즈니스용 OneDrive 및 SharePoint Online에서 데이터 보안을 위한 암호화의 기본 요소를 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="81b8f-104">Understand the basic elements of encryption for data security in OneDrive for Business and SharePoint Online.</span></span>
  
## <a name="security-and-data-encryption-in-office-365"></a><span data-ttu-id="81b8f-105">Office 365의 보안 및 데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="81b8f-105">Security and data encryption in Office 365</span></span>

<span data-ttu-id="81b8f-106">Microsoft 365는 실제 데이터 센터 보안, 네트워크 보안, 액세스 보안, 응용 프로그램 보안, 데이터 보안 등 여러 계층에 광범위 한 보호를 제공 하는 강력한 보안 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="81b8f-106">Microsoft 365 is a highly secure environment that offers extensive protection in multiple layers: physical data center security, network security, access security, application security, and data security.</span></span> <span data-ttu-id="81b8f-107">이 문서에서는 특히 비즈니스용 OneDrive 및 SharePoint Online에 대한 전송 중 및 보관된 데이터 보안의 암호화 측면을 중점적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="81b8f-107">This article specifically focuses on the in-transit and at-rest encryption side of data security for OneDrive for Business and SharePoint Online.</span></span>
  
<span data-ttu-id="81b8f-108">다음 비디오에서 데이터 암호화 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="81b8f-108">Watch how data encryption works in the following video.</span></span>
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a><span data-ttu-id="81b8f-109">전송 중인 데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="81b8f-109">Encryption of data in transit</span></span>

<span data-ttu-id="81b8f-110">비즈니스용 OneDrive 및 SharePoint Online에는 데이터 센터를 시작 및 종료하는 데이터에 대한 두 가지 시나리오가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81b8f-110">In OneDrive for Business and SharePoint Online, there are two scenarios in which data enters and exits the datacenters.</span></span>
  
- <span data-ttu-id="81b8f-111">**Client communication with the server** Communication to OneDrive for Business across the Internet uses SSL/TLS connections.</span><span class="sxs-lookup"><span data-stu-id="81b8f-111">**Client communication with the server** Communication to OneDrive for Business across the Internet uses SSL/TLS connections.</span></span> <span data-ttu-id="81b8f-112">All SSL connections are established using 2048-bit keys.</span><span class="sxs-lookup"><span data-stu-id="81b8f-112">All SSL connections are established using 2048-bit keys.</span></span>

- <span data-ttu-id="81b8f-113">**Data movement between datacenters** The primary reason to move data between datacenters is for geo-replication to enable disaster recovery.</span><span class="sxs-lookup"><span data-stu-id="81b8f-113">**Data movement between datacenters** The primary reason to move data between datacenters is for geo-replication to enable disaster recovery.</span></span> <span data-ttu-id="81b8f-114">For instance, SQL Server transaction logs and blob storage deltas travel along this pipe.</span><span class="sxs-lookup"><span data-stu-id="81b8f-114">For instance, SQL Server transaction logs and blob storage deltas travel along this pipe.</span></span> <span data-ttu-id="81b8f-115">While this data is already transmitted by using a private network, it is further protected with best-in-class encryption.</span><span class="sxs-lookup"><span data-stu-id="81b8f-115">While this data is already transmitted by using a private network, it is further protected with best-in-class encryption.</span></span> 

## <a name="encryption-of-data-at-rest"></a><span data-ttu-id="81b8f-116">보관된 데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="81b8f-116">Encryption of data at rest</span></span>

<span data-ttu-id="81b8f-117">보관된 암호화에는 두 가지 구성 요소가 포함되어 있습니다. 고객 콘텐츠의 BitLocker 디스크 수준 암호화 및 파일 단위 암호화입니다.</span><span class="sxs-lookup"><span data-stu-id="81b8f-117">Encryption at rest includes two components: BitLocker disk-level encryption and per-file encryption of customer content.</span></span>
  
<span data-ttu-id="81b8f-118">BitLocker는 서비스 전반에서 비즈니스용 OneDrive 및 SharePoint Online에 배포되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81b8f-118">BitLocker is deployed for OneDrive for Business and SharePoint Online across the service.</span></span> <span data-ttu-id="81b8f-119">파일 단위 암호화는 비즈니스용 OneDrive 및 Microsoft 365 다중 테 넌 트의 SharePoint Online 및 다중 테 넌 트 기술에서 구축 된 새로운 전용 환경에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81b8f-119">Per-file encryption is also in OneDrive for Business and SharePoint Online in Microsoft 365 multi-tenant and new dedicated environments that are built on multi-tenant technology.</span></span>
  
<span data-ttu-id="81b8f-120">While BitLocker encrypts all data on a disk, per-file encryption goes even further by including a unique encryption key for each file.</span><span class="sxs-lookup"><span data-stu-id="81b8f-120">While BitLocker encrypts all data on a disk, per-file encryption goes even further by including a unique encryption key for each file.</span></span> <span data-ttu-id="81b8f-121">Further, every update to every file is encrypted using its own encryption key.</span><span class="sxs-lookup"><span data-stu-id="81b8f-121">Further, every update to every file is encrypted using its own encryption key.</span></span> <span data-ttu-id="81b8f-122">Before they're stored, the keys to the encrypted content are stored in a physically separate location from the content.</span><span class="sxs-lookup"><span data-stu-id="81b8f-122">Before they're stored, the keys to the encrypted content are stored in a physically separate location from the content.</span></span> <span data-ttu-id="81b8f-123">Every step of this encryption uses Advanced Encryption Standard (AES) with 256-bit keys and is Federal Information Processing Standard (FIPS) 140-2 compliant.</span><span class="sxs-lookup"><span data-stu-id="81b8f-123">Every step of this encryption uses Advanced Encryption Standard (AES) with 256-bit keys and is Federal Information Processing Standard (FIPS) 140-2 compliant.</span></span> <span data-ttu-id="81b8f-124">The encrypted content is distributed across a number of containers throughout the datacenter, and each container has unique credentials.</span><span class="sxs-lookup"><span data-stu-id="81b8f-124">The encrypted content is distributed across a number of containers throughout the datacenter, and each container has unique credentials.</span></span> <span data-ttu-id="81b8f-125">These credentials are stored in a separate physical location from either the content or the content keys.</span><span class="sxs-lookup"><span data-stu-id="81b8f-125">These credentials are stored in a separate physical location from either the content or the content keys.</span></span>
  
<span data-ttu-id="81b8f-126">FIPS 140-2 준수에 대 한 자세한 내용은 [fips 140-2 준수](https://go.microsoft.com/fwlink/?LinkId=517625)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="81b8f-126">For additional information about FIPS 140-2 compliance, see [FIPS 140-2 Compliance](https://go.microsoft.com/fwlink/?LinkId=517625).</span></span>
  
<span data-ttu-id="81b8f-127">File-level encryption at rest takes advantage of blob storage to provide for virtually unlimited storage growth and to enable unprecedented protection.</span><span class="sxs-lookup"><span data-stu-id="81b8f-127">File-level encryption at rest takes advantage of blob storage to provide for virtually unlimited storage growth and to enable unprecedented protection.</span></span> <span data-ttu-id="81b8f-128">All customer content in OneDrive for Business and SharePoint Online will be migrated to blob storage.</span><span class="sxs-lookup"><span data-stu-id="81b8f-128">All customer content in OneDrive for Business and SharePoint Online will be migrated to blob storage.</span></span> <span data-ttu-id="81b8f-129">Here's how that data is secured:</span><span class="sxs-lookup"><span data-stu-id="81b8f-129">Here's how that data is secured:</span></span>
  
1. <span data-ttu-id="81b8f-130">All content is encrypted, potentially with multiple keys, and distributed across the datacenter.</span><span class="sxs-lookup"><span data-stu-id="81b8f-130">All content is encrypted, potentially with multiple keys, and distributed across the datacenter.</span></span> <span data-ttu-id="81b8f-131">Each file to be stored is broken into one or more chunks, depending its size.</span><span class="sxs-lookup"><span data-stu-id="81b8f-131">Each file to be stored is broken into one or more chunks, depending its size.</span></span> <span data-ttu-id="81b8f-132">Then, each chunk is encrypted using its own unique key.</span><span class="sxs-lookup"><span data-stu-id="81b8f-132">Then, each chunk is encrypted using its own unique key.</span></span> <span data-ttu-id="81b8f-133">Updates are handled similarly: the set of changes, or deltas, submitted by a user is broken into chunks, and each is encrypted with its own key.</span><span class="sxs-lookup"><span data-stu-id="81b8f-133">Updates are handled similarly: the set of changes, or deltas, submitted by a user is broken into chunks, and each is encrypted with its own key.</span></span>

2. <span data-ttu-id="81b8f-134">All of these chunks—files, pieces of files, and update deltas—are stored as blobs in our blob store.</span><span class="sxs-lookup"><span data-stu-id="81b8f-134">All of these chunks—files, pieces of files, and update deltas—are stored as blobs in our blob store.</span></span> <span data-ttu-id="81b8f-135">They also are randomly distributed across multiple blob containers.</span><span class="sxs-lookup"><span data-stu-id="81b8f-135">They also are randomly distributed across multiple blob containers.</span></span>

3. <span data-ttu-id="81b8f-136">해당 구성 요소에서 파일을 구성하는 데 사용되는 "맵"은 콘텐츠 데이터베이스에 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="81b8f-136">The "map" used to re-assemble the file from its components is stored in the Content Database.</span></span>

4. <span data-ttu-id="81b8f-137">Each blob container has its own unique credentials per access type (read, write, enumerate, and delete).</span><span class="sxs-lookup"><span data-stu-id="81b8f-137">Each blob container has its own unique credentials per access type (read, write, enumerate, and delete).</span></span> <span data-ttu-id="81b8f-138">Each set of credentials is held in the secure Key Store and is regularly refreshed.</span><span class="sxs-lookup"><span data-stu-id="81b8f-138">Each set of credentials is held in the secure Key Store and is regularly refreshed.</span></span>

<span data-ttu-id="81b8f-139">즉, 보관된 파일별 암호화에 관련된 세 가지 유형의 저장소가 있으며 각 저장소에는 고유한 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81b8f-139">In other words, there are three different types of stores involved in per-file encryption at rest, each with a distinct function:</span></span>
  
- <span data-ttu-id="81b8f-140">Content is stored as encrypted blobs in the blob store.</span><span class="sxs-lookup"><span data-stu-id="81b8f-140">Content is stored as encrypted blobs in the blob store.</span></span> <span data-ttu-id="81b8f-141">The key to each chunk of content is encrypted and stored separately in the content database.</span><span class="sxs-lookup"><span data-stu-id="81b8f-141">The key to each chunk of content is encrypted and stored separately in the content database.</span></span> <span data-ttu-id="81b8f-142">The content itself holds no clue as to how it can be decrypted.</span><span class="sxs-lookup"><span data-stu-id="81b8f-142">The content itself holds no clue as to how it can be decrypted.</span></span>

- <span data-ttu-id="81b8f-143">The Content Database is a SQL Server database.</span><span class="sxs-lookup"><span data-stu-id="81b8f-143">The Content Database is a SQL Server database.</span></span> <span data-ttu-id="81b8f-144">It holds the map required to locate and reassemble all of the content blobs held in the blob store as well as the keys needed to decrypt those blobs.</span><span class="sxs-lookup"><span data-stu-id="81b8f-144">It holds the map required to locate and reassemble all of the content blobs held in the blob store as well as the keys needed to decrypt those blobs.</span></span>

<span data-ttu-id="81b8f-145">Each of these three storage components—the blob store, the Content Database, and the Key Store—is physically separate.</span><span class="sxs-lookup"><span data-stu-id="81b8f-145">Each of these three storage components—the blob store, the Content Database, and the Key Store—is physically separate.</span></span> <span data-ttu-id="81b8f-146">The information held in any one of the components is unusable on its own.</span><span class="sxs-lookup"><span data-stu-id="81b8f-146">The information held in any one of the components is unusable on its own.</span></span> <span data-ttu-id="81b8f-147">This provides an unprecedented level of security.</span><span class="sxs-lookup"><span data-stu-id="81b8f-147">This provides an unprecedented level of security.</span></span> <span data-ttu-id="81b8f-148">Without access to all three it is impossible to retrieve the keys to the chunks, decrypt the keys to make them usable, associate the keys with their corresponding chunks, decrypt any chunk, or reconstruct a document from its constituent chunks.</span><span class="sxs-lookup"><span data-stu-id="81b8f-148">Without access to all three it is impossible to retrieve the keys to the chunks, decrypt the keys to make them usable, associate the keys with their corresponding chunks, decrypt any chunk, or reconstruct a document from its constituent chunks.</span></span>
