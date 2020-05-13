---
title: 타사 데이터 보관
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 0ce338d5-3666-4a18-86ab-c6910ff408cc
ms.custom:
- seo-marvel-apr2020
description: 소셜 미디어 플랫폼, 인스턴트 메시징 플랫폼 및 문서 공동 작업 플랫폼에서 Microsoft 365 사서함으로 타사 데이터를 가져오는 방법에 대해 알아봅니다.
ms.openlocfilehash: 2d011fcb63e0ec9804ade62f9fdcd1dd95fbf798
ms.sourcegitcommit: ab0a944159d9349fbc7adc2f51c7f881254d7782
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "44210544"
---
# <a name="archive-third-party-data"></a>타사 데이터 보관

Microsoft 365에서는 관리자가 소셜 미디어 플랫폼, 인스턴트 메시징 플랫폼 및 문서 공동 작업 플랫폼에서 타사 데이터를 가져오고 Microsoft 365 조직의 사서함으로 보관할 수 있습니다. Microsoft 365로 가져올 수 있는 타사 데이터 원본의 예에는 다음 서비스가 포함 됩니다. 
  
- **공유:** Facebook, LinkedIn, Twitter 및 Yammer

- **인스턴트 메시징:** Yahoo Messenger 및 GoogleTalk

- **문서 공동 작업:** Box 및 DropBox

- **세로줄:** 고객 관계 관리 (예: Salesforce Chatter) 및 금융 서비스 (예: Bloomberg 및: Thomson Reuters)

- **SMS/문자 메시징:** BlackBerry

타사 데이터를 가져온 후에는이 데이터에 소송 보존, eDiscovery, 원본 위치 보관, 감사, 통신 준수 및 보존 정책과 같은 Microsoft 365 준수 기능을 적용할 수 있습니다. 예를 들어 사서함이 소송 보존 상태에 있는 경우 타사 데이터는 보존 됩니다. Microsoft eDiscovery 도구를 사용 하 여 타사 데이터를 검색할 수 있습니다. 또는 Microsoft 데이터에 대해 사용할 수 있는 것과 마찬가지로 보관 및 보존 정책을 타사 데이터에 적용할 수도 있습니다. 또한 Microsoft 365에서 타사 데이터를 보관 하면 조직이 정부 및 규정 정책을 준수 하는 데 도움이 될 수 있습니다.

Microsoft 365에서는 두 가지 방법으로 타사 데이터를 가져오고 보관할 수 있습니다.

- **보안 & 준수 센터에서 타사 데이터 커넥터를 사용 합니다.** Microsoft 365 준수 센터에서 제공 되는 사용자 지정 데이터 커넥터를 사용 합니다. 커넥터를 설정 하 고 구성한 후에는 타사 데이터 원본에 연결 하 고, 항목의 콘텐츠를 전자 메일 메시지 형식으로 변환한 다음 Microsoft 365에서 사서함으로 항목을 가져옵니다. 현재는 Facebook Business 페이지, 회사 Twitter 계정, LinkedIn, 인스턴트 Bloomberg 및 조직의 인적 자원 (HR) 데이터로 데이터를 가져오고 보관 하기 위한 커넥터를 구현할 수 있습니다. 이러한 커넥터 중 하나를 설정 하는 단계별 지침은 다음을 참조 하십시오.

   - **Facebook:** [커넥터를 사용 하 여 Facebook 데이터 보관 (미리 보기)](archive-facebook-data-with-sample-connector.md)

   - **Twitter:** [커넥터를 사용 하 여 Twitter 데이터를 보관 합니다 (미리 보기)](archive-twitter-data-with-sample-connector.md) .

   - **Linkedin:** [linkedin 데이터를 보관 하는 커넥터 설정](archive-linkedin-data.md)

   - **인스턴트 Bloomberg:** [인스턴트 Bloomberg 데이터를 보관 하는 커넥터 설정](archive-instant-bloomberg-data.md)

   - **Hr 데이터:** [hr 데이터를 가져오기 위한 연결선 설정 (미리 보기)](import-hr-data.md)

- **Microsoft 파트너와 함께 작업 합니다.** 조직에서는 타사 데이터 원본에서 정기적으로 항목을 추출 하 고 타사 API로 Microsoft 클라우드에 연결한 다음 해당 항목을 Microsoft 365로 가져오는 사용자 지정 커넥터를 제공 하는 Microsoft 파트너와 함께 작업 합니다. 또한 파트너 커넥터는 타사 데이터 원본에서 전자 메일 메시지로 항목의 콘텐츠를 변환한 다음 Microsoft 365에서 사서함으로 가져옵니다. 사용할 수 있는 파트너의 목록과이 방법의 단계별 프로세스에 대 한 자세한 내용은 [Microsoft 365에서 파트너와 협력 하 여 타사 데이터 보관](work-with-partner-to-archive-third-party-data.md)을 참조 하십시오.
