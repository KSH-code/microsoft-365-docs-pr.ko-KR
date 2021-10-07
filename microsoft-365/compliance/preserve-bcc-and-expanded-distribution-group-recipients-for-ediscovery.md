---
title: eDiscovery의 숨은 참조 및 확장된 메일 그룹 수신자 보존
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/19/2017
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.assetid: eb8ddf15-0080-457e-9d83-e73e193da334
description: In-Place, 소송 보존 및 Microsoft 365 보존 정책을 사용하면 규정 준수 및 eDiscovery 요구 사항을 충족하기 위해 사서함 콘텐츠를 보존할 수 있습니다.
ms.openlocfilehash: f034129400a47e9b72f0883ce368ecea657851a5
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60175134"
---
# <a name="preserve-bcc-and-expanded-distribution-group-recipients-for-ediscovery"></a>eDiscovery의 숨은 참조 및 확장된 메일 그룹 수신자 보존
  
소송 보존, eDiscovery 보류 및 [](./retention.md) Microsoft 365 보존 정책(Microsoft 365 규정 준수 센터)을 사용하면 규정 준수 및 eDiscovery 요구 사항을 충족하기 위해 사서함 콘텐츠를 보존할 수 있습니다. 메시지의 받는 사람 및Cc 필드에서 직접 주소가 지정되는 받는 사람에 대한 정보는 기본적으로 모든 메시지에 포함됩니다. 그러나 조직에서 메시지의 모든 받는 사람에 대한 세부 정보를 검색하고 재현하는 기능을 필요로 할 수 있습니다. 여기에는 다음이 포함됩니다.
  
- **메시지의 Bcc 필드를 사용하여 주소가 있는 받는 사람:** Bcc 받는 사람은 보낸 사람의 사서함에 메시지에 저장되지만 받는 사람에게 배달된 메시지의 헤더에는 포함되지 않습니다. 
    
- **확장된 메일 그룹 받는 사람:** 받는 사람,Cc 또는 Bcc 필드에서 메시지가 주소가 있는 메일 그룹의 구성원이기 때문에 메시지를 받는 사람입니다. 
    
Exchange Online 및 Exchange Server 2013(누적 업데이트 7 이상 버전)에는 Bcc 및 확장된 메일 그룹 받는 사람에 대한 정보가 유지됩니다. eDiscovery 도구를 사용하여 이 정보를 검색할 수 Microsoft 365 규정 준수 센터. 
  
## <a name="how-bcc-recipients-and-expanded-distribution-group-recipients-are-preserved"></a>Bcc 받는 사람 및 확장된 메일 그룹 받는 사람을 보존하는 방법

앞에서 말한 대로 Bcc의 ed 받는 사람에 대한 정보는 보낸 사람의 사서함에 메시지와 함께 저장됩니다. 이 정보는 인덱싱된 후 eDiscovery 검색 및 보류에 사용할 수 있습니다. 
  
사서함을 보류 또는 소송 보류로 설정한 후 확장된 메일 그룹 받는 사람에 대한 In-Place 저장됩니다. 이 Office 365 이 정보는 사서함에 Microsoft 365 보존 정책이 적용될 때도 저장됩니다. 메일 그룹 구성원은 메시지를 보낼 때 결정됩니다. 메시지와 함께 저장된 확장된 받는 사람 목록은 메시지가 전송된 후 그룹의 구성원 자격에 대한 변경 내용의 영향을 되지 않습니다. 
  
| 정보 | 에 저장됩니다. | 기본적으로 저장되어 있나요? | 액세스 가능... |
|:-----|:-----|:-----|:-----|
|받는 사람 및Cc 받는 사람  <br/> |보낸 사람 및 받는 사람 사서함의 메시지 속성  <br/> |예  <br/> |보낸 사람, 받는 사람 및 규정 준수 담당자  <br/> |
|Bcc 받는 사람  <br/> |보낸 사람 사서함의 메시지 속성  <br/> |예  <br/> |보낸 사람 및 규정 준수 담당자  <br/> |
|확장된 메일 그룹 받는 사람  <br/> |보낸 사람 사서함의 메시지 속성  <br/> |아니요. 사서함이 보류 또는 소송 보존으로 설정되거나 In-Place 보존 정책에 할당된 후 확장된 메일 그룹 받는 사람 Microsoft 365 저장됩니다.  <br/> |규정 준수 관리자  <br/> |
   
## <a name="searching-for-messages-sent-to-bcc-and-expanded-distribution-group-recipients"></a>Bcc 및 확장된 메일 그룹 받는 사람에게 보낸 메시지 검색

받는 사람에게 보낸 메시지를 검색할 때 eDiscovery 검색 결과에는 이제 받는 사람이 구성원으로 있는 메일 그룹으로 보낸 메시지가 포함됩니다. 다음 표에서는 Bcc 및 확장된 메일 그룹 받는 사람에게 전송된 메시지가 eDiscovery 검색에서 반환되는 시나리오를 보여줍니다.
  
시나리오 1: John은 US-Sales 메일 그룹의 구성원입니다. 이 표에는 Bob이 메일 그룹을 통해 직접 또는 간접적으로 John에게 메시지를 보낼 때 eDiscovery 검색 결과가 표시됩니다.
  
| Bob의 사서함에서 보낸 메시지를 검색할 때... | 그리고 메시지가 다음과 함께 전송됩니다. | 결과에 메시지가 포함되어 있나요? |
|:-----|:-----|:-----|
|To:John  <br/> |John on TO  <br/> |예  <br/> |
|To:John  <br/> |US-Sales ON  <br/> |예  <br/> |
|To:US-Sales  <br/> |US-Sales ON  <br/> |예  <br/> |
|Cc:John  <br/> |John on CC  <br/> |예  <br/> |
|Cc:John  <br/> |US-Sales CC의 경우  <br/> |예  <br/> |
|Cc:US-Sales  <br/> |US-Sales CC의 경우  <br/> |예  <br/> |
   
시나리오 2: Bob은 John(To/Cc) 및 잭(Bcc 직접 또는 메일 그룹을 통해 간접적으로)에게 전자 메일을 전송합니다. 아래 표에는 eDiscovery 검색 결과가 표시됩니다.
  
| 검색할 때... | 보낸 메시지의 경우... | 결과에 메시지가 포함되어 있나요? | 참고 |
|:-----|:-----|:-----|:-----|
|Bob의 사서함  <br/> |To/Cc:John  <br/> |예  <br/> |잭이 Bcc'ed인 표시를 제공합니다.  <br/> |
|Bob의 사서함  <br/> |Bcc:Jack  <br/> |예  <br/> |잭이 Bcc'ed인 표시를 제공합니다.  <br/> |
|Bob의 사서함  <br/> |Bcc:Jack(메일 그룹을 통해)  <br/> |예  <br/> |메시지를 보낼 때 확장된 Bcc'ed 메일 그룹의 구성원 목록은 eDiscovery 검색 미리 보기, 내보내기 및 로그에 표시됩니다.  <br/> |
|John의 사서함  <br/> |To/Cc:John  <br/> |예  <br/> |Bcc 받는 사람을 표시하지 않습니다.  <br/> |
|John의 사서함  <br/> |Bcc:Jack(직접 또는 메일 그룹을 통해)  <br/> |아니요  <br/> |Bcc 정보는 받는 사람에게 배달된 메시지에 저장되지 않습니다. 보낸 사람 사서함을 검색해야 합니다.  <br/> |
|잭의 사서함  <br/> |To/Cc:John(직접 또는 메일 그룹을 통해)  <br/> |예  <br/> |받는 사람/Cc 정보는 모든 받는 사람에게 배달되는 메시지에 포함됩니다.  <br/> |
|잭의 사서함  <br/> |Bcc:Jack(직접 또는 메일 그룹을 통해)  <br/> |아니요  <br/> |Bcc 정보는 받는 사람에게 배달된 메시지에 저장되지 않습니다. 보낸 사람 사서함을 검색해야 합니다.  <br/> |
   
## <a name="frequently-asked-questions"></a>자주 묻는 질문

 **Q. Bcc 받는 사람 정보가 저장되는 위치는 언제 어디인가요?**
  
대답. 보낸 사람의 사서함에 있는 원본 메시지에 기본적으로 Bcc 받는 사람 정보가 보존됩니다. Bcc 받는 사람이 메일 그룹인 경우 메일 그룹 구성원은 보낸 사람의 사서함이 보류 중이거나 보존 정책에 할당된 Microsoft 365 확장됩니다.
  
 **Q. 확장된 메일 그룹 받는 사람 목록은 언제 어디서 저장하나요?**
  
대답. 그룹 구성원은 메시지를 보낼 때 확장됩니다. 확장된 메일 그룹 구성원 목록은 보낸 사람 사서함의 원본 메시지에 저장됩니다. 보낸 사람 사서함이 보류 중이거나 In-Place 보존 정책에 할당되어 있어야 Microsoft 365 합니다.
  
 **Q. 받는 사람/참조 받는 사람이 Bcc로 ed인 받는 사람을 볼 수 있나요?**
  
대답. 아니요. 이 정보는 메시지 헤더에 포함되지 않습니다. 받는 사람/Cc 받는 사람에게는 표시되지 않습니다. 보낸 사람이 사서함에 저장된 원본 메시지에 저장된 Bcc 필드를 볼 수 있습니다. 준수 담당자는 보낸 사람 사서함을 검색할 때 이 정보를 볼 수 있습니다.
  
 **Q. 확장된 메일 그룹 받는 사람이 항상 보존되도록 하는 방법**
  
대답. 확장된 메일 그룹 구성원이 항상 메시지와 함께 [](/Exchange/policy-and-compliance/holds/place-all-mailboxes-on-hold) 보존되도록 설정하기 위해 모든 사서함을 보류하거나 조직 전체의 사서함 보존 정책을 Microsoft 365 합니다. 
  
 **Q. 지원되는 그룹 유형은 무엇입니까?**
  
대답. 메일 그룹, 메일 사용이 가능한 보안 그룹 및 동적 메일 그룹이 지원됩니다. 
  
 **Q. 메시지에 확장 및 저장되는 메일 그룹 받는 사람 수에 제한이 있나요?**
  
대답. 메일 그룹의 구성원을 최대 10,000명까지 보존합니다.
  
 **Q. 중첩된 메일 그룹이 지원하나요?**
  
대답. 예. 중첩된 메일 그룹의 25개 수준이 확장됩니다.
  
 **Q. Bcc 및 확장된 메일 그룹 받는 사람 정보가 표시되는 위치는 어디인가요?**
  
대답. eDiscovery 검색을 수행할 때 준수 책임자에게는 Bcc 및 확장된 메일 그룹 받는 사람 정보가 표시됩니다. Bcc 및 확장된 메일 그룹 받는 사람은 검색 사서함에 복사되거나 PST 파일로 내보내는 검색 결과에 포함되고 검색 결과에 포함된 eDiscovery 로그에 포함됩니다. 검색 미리 보기에서도 Bcc 받는 사람 정보를 사용할 수 있습니다.
  
 **Q. 메일 그룹의 구성원이 조직의 GAL(전체 주소 목록)에서 숨겨져 있는 경우 어떻게 하나요?**
  
대답. 영향이 없음 받는 사람이 GAL에서 숨겨져 있는 경우 확장된 메일 그룹의 받는 사람 목록에 계속 포함됩니다.