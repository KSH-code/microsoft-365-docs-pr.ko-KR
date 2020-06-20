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
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a>비즈니스용 OneDrive 및 SharePoint Online에서의 데이터 암호화

비즈니스용 OneDrive 및 SharePoint Online에서 데이터 보안을 위한 암호화의 기본 요소를 이해합니다.
  
## <a name="security-and-data-encryption-in-office-365"></a>Office 365의 보안 및 데이터 암호화

Microsoft 365는 실제 데이터 센터 보안, 네트워크 보안, 액세스 보안, 응용 프로그램 보안, 데이터 보안 등 여러 계층에 광범위 한 보호를 제공 하는 강력한 보안 환경입니다. 이 문서에서는 특히 비즈니스용 OneDrive 및 SharePoint Online에 대한 전송 중 및 보관된 데이터 보안의 암호화 측면을 중점적으로 설명합니다.
  
다음 비디오에서 데이터 암호화 방법을 알아보세요.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a>전송 중인 데이터 암호화

비즈니스용 OneDrive 및 SharePoint Online에는 데이터 센터를 시작 및 종료하는 데이터에 대한 두 가지 시나리오가 있습니다.
  
- **Client communication with the server** Communication to OneDrive for Business across the Internet uses SSL/TLS connections. All SSL connections are established using 2048-bit keys.

- **Data movement between datacenters** The primary reason to move data between datacenters is for geo-replication to enable disaster recovery. For instance, SQL Server transaction logs and blob storage deltas travel along this pipe. While this data is already transmitted by using a private network, it is further protected with best-in-class encryption. 

## <a name="encryption-of-data-at-rest"></a>보관된 데이터 암호화

보관된 암호화에는 두 가지 구성 요소가 포함되어 있습니다. 고객 콘텐츠의 BitLocker 디스크 수준 암호화 및 파일 단위 암호화입니다.
  
BitLocker는 서비스 전반에서 비즈니스용 OneDrive 및 SharePoint Online에 배포되고 있습니다. 파일 단위 암호화는 비즈니스용 OneDrive 및 Microsoft 365 다중 테 넌 트의 SharePoint Online 및 다중 테 넌 트 기술에서 구축 된 새로운 전용 환경에도 사용 됩니다.
  
While BitLocker encrypts all data on a disk, per-file encryption goes even further by including a unique encryption key for each file. Further, every update to every file is encrypted using its own encryption key. Before they're stored, the keys to the encrypted content are stored in a physically separate location from the content. Every step of this encryption uses Advanced Encryption Standard (AES) with 256-bit keys and is Federal Information Processing Standard (FIPS) 140-2 compliant. The encrypted content is distributed across a number of containers throughout the datacenter, and each container has unique credentials. These credentials are stored in a separate physical location from either the content or the content keys.
  
FIPS 140-2 준수에 대 한 자세한 내용은 [fips 140-2 준수](https://go.microsoft.com/fwlink/?LinkId=517625)를 참조 하세요.
  
File-level encryption at rest takes advantage of blob storage to provide for virtually unlimited storage growth and to enable unprecedented protection. All customer content in OneDrive for Business and SharePoint Online will be migrated to blob storage. Here's how that data is secured:
  
1. All content is encrypted, potentially with multiple keys, and distributed across the datacenter. Each file to be stored is broken into one or more chunks, depending its size. Then, each chunk is encrypted using its own unique key. Updates are handled similarly: the set of changes, or deltas, submitted by a user is broken into chunks, and each is encrypted with its own key.

2. All of these chunks—files, pieces of files, and update deltas—are stored as blobs in our blob store. They also are randomly distributed across multiple blob containers.

3. 해당 구성 요소에서 파일을 구성하는 데 사용되는 "맵"은 콘텐츠 데이터베이스에 저장됩니다.

4. Each blob container has its own unique credentials per access type (read, write, enumerate, and delete). Each set of credentials is held in the secure Key Store and is regularly refreshed.

즉, 보관된 파일별 암호화에 관련된 세 가지 유형의 저장소가 있으며 각 저장소에는 고유한 기능이 있습니다.
  
- Content is stored as encrypted blobs in the blob store. The key to each chunk of content is encrypted and stored separately in the content database. The content itself holds no clue as to how it can be decrypted.

- The Content Database is a SQL Server database. It holds the map required to locate and reassemble all of the content blobs held in the blob store as well as the keys needed to decrypt those blobs.

Each of these three storage components—the blob store, the Content Database, and the Key Store—is physically separate. The information held in any one of the components is unusable on its own. This provides an unprecedented level of security. Without access to all three it is impossible to retrieve the keys to the chunks, decrypt the keys to make them usable, associate the keys with their corresponding chunks, decrypt any chunk, or reconstruct a document from its constituent chunks.
