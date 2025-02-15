---
title: 비즈니스용 OneDrive 및 SharePoint Online에서의 데이터 암호화
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 9/20/2021
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- SPO160
- MET150
ms.assetid: 6501b5ef-6bf7-43df-b60d-f65781847d6c
ms.collection:
- M365-security-compliance
- SPO_Content
description: 비즈니스용 OneDrive 및 SharePoint Online에서 데이터 보안을 위한 암호화의 기본 요소를 이해합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 25bebc8fd5ab9b820667f5220785b021230ca6e1
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170766"
---
# <a name="data-encryption-in-onedrive-for-business-and-sharepoint-online"></a>비즈니스용 OneDrive 및 SharePoint Online에서의 데이터 암호화

비즈니스용 OneDrive 및 SharePoint Online에서 데이터 보안을 위한 암호화의 기본 요소를 이해합니다.
  
## <a name="security-and-data-encryption-in-office-365"></a>보안 및 데이터 암호화를 Office 365

Microsoft 365 보안은 물리적 데이터 센터 보안, 네트워크 보안, 액세스 보안, 응용 프로그램 보안 및 데이터 보안과 같은 여러 계층에서 광범위한 보호를 제공하는 매우 안전한 환경입니다. 이 문서에서는 특히 비즈니스용 OneDrive 및 SharePoint Online에 대한 전송 중 및 보관된 데이터 보안의 암호화 측면을 중점적으로 설명합니다.
  
다음 비디오에서 데이터 암호화 방법을 알아보세요.
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/dea0dec4-4077-4095-9a32-19b94ea2da4b?autoplay=false]
  
## <a name="encryption-of-data-in-transit"></a>전송 중인 데이터 암호화

비즈니스용 OneDrive 및 SharePoint Online에는 데이터 센터를 시작 및 종료하는 데이터에 대한 두 가지 시나리오가 있습니다.
  
- **서버와 통신하는 클라이언트** SSL/TLS 연결을 사용하는 인터넷을 통해 비즈니스용 OneDrive와 통신합니다. 모든 SSL 연결이 2048비트 키를 사용하여 설정됩니다.

- **데이터 센터 간 데이터 이동** 데이터 센터 간에 데이터를 이동하는 주된 이유는 재해 복구를 사용하도록 설정하기 위한 지리적 복제 때문입니다. 예를 들어 SQL Server 트랜잭션 로그 및 Blob Storage 델타가 이 파이프를 따라 이동합니다. 이 데이터는 개인 네트워크를 사용하여 이미 전송되었지만 최고급 암호화로 추가 보호됩니다. 

## <a name="encryption-of-data-at-rest"></a>보관된 데이터 암호화

보관된 암호화에는 두 가지 구성 요소가 포함되어 있습니다. 고객 콘텐츠의 BitLocker 디스크 수준 암호화 및 파일 단위 암호화입니다.
  
BitLocker는 서비스 전반에서 비즈니스용 OneDrive 및 SharePoint Online에 배포되고 있습니다. 파일당 암호화는 다중 테넌트 기술을 비즈니스용 OneDrive SharePoint 새로운 전용 Microsoft 365 환경의 비즈니스용 OneDrive Online에도 있습니다.
  
BitLocker는 디스크에서 모든 데이터를 암호화하는 동안 각 파일에 대해 고유한 암호화 키를 포함하여 파일 단위 암호화를 추가로 수행합니다. 또한 모든 파일에 대한 모든 업데이트는 자체 암호화 키를 사용하여 암호화됩니다. 암호화된 콘텐츠에 대한 키는 콘텐츠와 물리적으로 분리된 위치에 저장됩니다. 이 암호화의 모든 단계는 AES(Advanced Encryption Standard) 256비트 키를 사용하며 FIPS(Federal Information Processing Standard) 140-2 규정을 준수합니다. 암호화된 콘텐츠는 데이터 센터 전반에 걸쳐 여러 컨테이너에 분산되며 각 컨테이너에는 고유한 자격 증명이 있습니다. 이러한 자격 증명은 콘텐츠 또는 콘텐츠 키에서 물리적으로 분리된 위치에 저장됩니다.
  
FIPS 140-2 규정 준수에 대한 자세한 내용은 [FIPS 140-2 준수를 참조하세요.](/previous-versions/sql/sql-server-2008-r2/bb326611(v=sql.105))
  
보관된 파일 수준 암호화는 Blob Storage를 활용하여 거의 무제한의 저장 용량을 제공하며 비교할 수 없는 보호 기능을 사용합니다. 비즈니스용 OneDrive 및 SharePoint Online의 모든 고객 콘텐츠는 Blob Storage로 마이그레이션됩니다. 이러한 데이터를 보호하는 방법은 다음과 같습니다.
  
1. 모든 콘텐츠가 잠재적으로 여러 개의 키를 사용하여 암호화되고 데이터 센터에 분산됩니다. 저장할 각 파일은 크기에 따라 하나 이상의 청크로 분할됩니다. 그런 다음, 각 청크는 자체 고유 키를 사용하여 암호화됩니다. 업데이트를 유사하게 처리: 사용자가 제출한 변경 내용 집합 또는 델타가 청크로 분할되고 각 청크는 자체 고유 키를 사용하여 암호화됩니다.

2. 이러한 모든 청크(파일, 파일 부분 및 델타 업데이트)는 Blob 저장소에서 Blob으로 저장됩니다. 또한 여러 개의 Blob 컨테이너에 임의로 분산됩니다.

3. 해당 구성 요소에서 파일을 구성하는 데 사용되는 "맵"은 콘텐츠 데이터베이스에 저장됩니다.

4. 각 Blob 컨테이너에는 액세스 유형(읽기, 쓰기, 열거 및 삭제)별로 각각의 고유한 자격 증명이 있습니다. 각 자격 증명 집합이 보안 키 저장소에 보관되고 정기적으로 새로 고쳐집니다.

즉, 보관된 파일별 암호화에 관련된 세 가지 유형의 저장소가 있으며 각 저장소에는 고유한 기능이 있습니다.
  
- 콘텐츠는 Blob 저장소에 암호화된 Blob으로 저장됩니다. 콘텐츠의 각 청크에 대한 키는 암호화되어 콘텐츠 데이터베이스에 별도로 저장됩니다. 콘텐츠 자체는 암호를 해독하는 방법에 대한 단서를 가지고 있지 않습니다.

- 콘텐츠 데이터베이스는 SQL Server 데이터베이스입니다. Blob 저장소에 보관된 모든 콘텐츠 Blob을 찾고 다시 구성하는 데 필요한 맵뿐만 아니라 해당 Blob을 암호 해독하는 데 필요한 키도 가지고 있습니다.

이러한 3개의 저장소 구성 요소는 Blob 저장소, 콘텐츠 데이터베이스 및 키 저장소이며 각 저장소는 물리적으로 분리되어 있습니다. 구성 요소 중 하나에 보관된 정보를 자체적으로 사용할 수는 없습니다. 전례 없는 수준의 보안을 제공합니다. 3개의 모든 저장소에 대한 액세스 권한이 없으면 청크에 대한 키 검색, 키를 사용할 수 있도록 암호 해독, 키를 해당 청크와 연결, 모든 청크 암호 해독 또는 해당 구성 청크에서 문서 다시 생성을 수행할 수 없습니다.