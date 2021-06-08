---
title: FAQ에 Microsoft 365 스케줄러
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: FAQ에 Microsoft 365 스케줄러
ms.openlocfilehash: d4cedf420dd605d04328b7f1edeabbd4e1bb5ac7
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809170"
---
# <a name="scheduler-for-microsoft-365-faqs"></a>FAQ에 Microsoft 365 스케줄러

**질문:** Scheduler는 cortana for Windows, *Daily Briefing Email* 및 *Play My Emails와* 같은 다른 *Cortana* 기능과 어떻게 통합하나요?</br>
스케줄러는 다른 Cortana 기능과는 독립적인 서비스입니다. 다른 Cortana 기능은 테넌트 수준에서 사용하지 않도록 설정할 수 있으며, 여전히 전자 메일 주소를 사용하여 스케줄러를 cortana@yourdomain.com 있습니다. 현재 사용자는 전자 메일을 통해서만 스케줄러와 상호 작용할 수 있습니다.

**질문:** 이 방식은 모든 작업에서만 Outlook? 다른 전자 메일 제품이 지원하나요?</br>
위의 세 가지 요구 사항 외 라이선스가 있는 한 사용자는 모든 cortana@yourdomain.com 전자 메일 클라이언트에서 전자 메일을 보낼 수 있습니다.

**질문:** 연락처가 OUTLOOK GAL 또는 다른 회사에 해당하는 개인 연락처 목록에 있을 수 있나요?</br>
모임 참석자는 회사 내부 또는 외부의 전자 메일 주소가 있는 모든 사람이 될 수 있습니다. 안타깝게도 스케줄러는 오늘 GAL에서 이름을 찾아서 자동으로 이름을 전자 메일 주소/별칭으로 변환할 수 없습니다.

**질문:** 설치된 버전의 스케줄러(사내) 버전과 함께 스케줄러를 사용할 수 Outlook?</br>
스케줄러를 사용하려면 Exchange Online. 프레미스(Exchange Server)에서 작동하지 않습니다. 모든 전자 메일 클라이언트, 데스크톱, Outlook, iOS, android, gmail 등에서 작동합니다.

**질문:** 백그라운드에서 Outlook 열려야 합니까?</br>
Outlook 백그라운드에서 열 필요가 없습니다. Cortana에 메일을 보내고 이를 통해 대량 작업을 하는 데만 Cortana를 보내면 됩니다.

## <a name="frequently-asked-trust-and-privacy-questions"></a>자주 묻는 신뢰 및 개인 정보 관련 질문

**질문:** 스케줄러는 어떻게 작동하나요?</br>
스케줄러는 휴먼 도우미로 강화된 AI(일정 인텔리전스)를 사용 합니다. AI 모델이 Cortana와의 자연스러운 통신을 지원해야 하는 경우 모임 요청은 검토 및 완료를 위해 사람으로 에스컬레이터됩니다.

**질문:** Who 에스컬레이터 요청을 검토하는 사람이 있습니까? </br>
스케줄러 도우미는 개인 및 기밀 정보에 대해 인증된 Microsoft SSPA(공급자 보안 및 개인 정보 보호 보증)입니다. 

**질문:** SSPA 도우미는 어떤 것을 볼 수 있나요?</br>
스케줄러 및 SSPA 도우미는 Cortana로 주소가 있는 전자 메일을 볼 수 있습니다. 스레드된 전자 메일 교환에서는 Cortana가 추가되기 전 스레드의 이전 전자 메일이 아니라 Cortana의 전자 메일 주소가 포함된 전자 메일만 처리됩니다.   

**질문:** 고객 데이터가 스케줄러의 데이터 센터에 Flow? </br>
스케줄러는 모든 고객 콘텐츠를 테넌트 경계 내에 저장하고 GDPR 지침, Microsoft 365 Trust & 개인 정보 취급 방침 및 테넌트 전자 메일 정책에 따라 데이터를 보존합니다.

**질문:** 스케줄러는 내부 참석자에 대한 무료/사용 중 데이터를 어떻게 처리하나요? </br>
스케줄러의 자동화는 *findMeetingTimes* 서비스를 사용하여 참석자 및 이끌이가 함께 사용할 수 있는 시간을 식별합니다. 이 서비스는 Outlook 모임 양식의  추천 시간과 같은 다른 Outlook 기능을 제공합니다. 무료/사용 중 참석자 정보는 명시적으로 사용 중이지 않습니다. 

**질문:** 스케줄러 GDPR이 규격인가요? </br>
예.

**질문:** Who Cortana 사서함에 액세스할 수 있나요? </br>
스케줄러는 테넌트의 Cortana 사서함으로 전송되는 모임 요청 및 관련 전자 메일을 처리합니다. Microsoft는 테넌트 관리자의 요청에 따라 Lockbox 승인을 통해서만 Cortana 사서함에 액세스할 수 없습니다.  

**질문:** 고객 데이터가 AI 모델을 교육하는 데 사용하나요?</br>
데이터 교육 집합에 사용할 Microsoft 365 스케줄러의 고객 콘텐츠는 사용할 수 없습니다. 모든 고객 콘텐츠는 고객 테넌트에 있습니다.  

**질문:** 스케줄러가 암호화된 메일을 처리하나요?</br>
아니요. 스케줄러 워크플로에서 암호화된 메일이 거부됩니다. 




