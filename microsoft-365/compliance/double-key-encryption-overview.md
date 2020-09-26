---
title: 이중 키 암호화 개요 및 FAQ
description: Microsoft 365의 이중 키 암호화에 대 한 질문과 대답
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 09/22/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 98c61e66155e21624e8ecba460ebc3041e72ada5
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277661"
---
# <a name="double-key-encryption-frequently-asked-questions"></a>이중 키 암호화에 대 한 질문과 대답

이중 키 암호화가 작동 하는 방식에 대 한 질문이 있나요? 여기에서 대답을 확인 하세요.

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a>Microsoft 365 (DKE)에 대 한 이중 키 암호화 란?

Microsoft 365에 대 한 이중 암호화를 사용 하면 고객이 전문화 된 요구 사항을 충족 하도록 중요 한 데이터를 보호할 수 있습니다. 고객은 암호화 키에 대 한 모든 권한을 유지 관리 하는 데 도움이 됩니다. 두 개의 키를 사용 하 여 데이터를 보호 합니다. 컨트롤의 한 가지 키와 Microsoft Azure에 안전 하 게 저장 되는 두 번째 키 이중 키 암호화로 보호 된 데이터를 보려면 두 키에 모두 액세스 해야 합니다. Microsoft는 이러한 키 중 하나에만 액세스할 수 있으므로, 보호 된 데이터는 Microsoft에 액세스 가능 하지 않으므로 데이터 개인 정보 및 보안에 대 한 모든 권한이 있는지 확인 해야 합니다.  

선택한 위치 (온-프레미스 키 관리 서버 또는 클라우드에서)에서 키를 요청 하는 데 사용 되는 이중 키 암호화 서비스를 호스트할 수 있습니다. 다른 응용 프로그램과 마찬가지로 서비스를 유지 관리 합니다. 이중 키 암호화를 사용 하면 이중 키 암호화 서비스에 대 한 액세스를 제어할 수 있습니다. 중요 한 데이터를 온-프레미스에 저장 하거나 클라우드로 이동할 수 있습니다. 키에 대 한 모든 권한을 유지 관리 하기 때문에 타사 액세스를 방지 하는 것이 확실 합니다. 이중 키 암호화를 사용 하면 데이터와 키를 같은 위치에 저장할 수 있습니다.

DKE는 일반 데이터 보호 규정 (GDPR), 건강 보험 이식성 및 책임 행동 (HIPAA), 금융-Gramm-leach-bliley-Gramm-leach-bliley Act (GLBA), 러시아의 데이터 지역화 법-연방 법과 같은 여러 규정 및 표준에서 규정 요구 사항을 충족 하는 데 도움이 됩니다. 242-FZ, 오스트레일리아의 연방 개인 정보 보호 Act 1988 및 뉴질랜드의 개인 정보 보호 Act 1993

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>Microsoft Office 기본 제공 민감도 레이블에 이중 키 암호화를 사용할 수 있나요?

이중 암호화로 문서를 보호 하려면 Azure Information Protection 통합 레이블 지정 클라이언트를 사용 해야 합니다. 현재는 Microsoft Office 기본 제공 민감도 레이블을 사용할 수 없습니다. 

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>DKE에 사용할 수 있는 Microsoft 365 앱은 무엇입니까?

Microsoft Word, Excel 및 PowerPoint의 데스크톱 버전을 사용 하 여 문서를 보호 하는 데에는 DKE 레이블을 사용할 수 있습니다. Windows에서 *. 12711 이상 (데스크톱 버전의 Word, PowerPoint 및 Excel)을 사용 하 고 있는지 확인 합니다.

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>이중 키 암호화가 기존 키 (HYOK) 솔루션에 어떤 차이가 있나요?

이중 키 암호화는 두 개의 키로 데이터를 암호화 합니다. 암호화 키가 컨트롤에 있고 두 번째 키가 Microsoft Azure에 저장 되므로 암호화 된 데이터를 클라우드로 이동할 수 있습니다. HYOK은 한 키로만 콘텐츠를 보호 하 고 키는 항상 온-프레미스입니다.  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>두 키 암호화 된 문서를 외부에서 공유할 수 있나요?

다음과 같은 사용자는 두 개의 암호화 된 문서를 별도의 테 넌 트에 있는 사용자와 공유할 수 있습니다.

- 키에 액세스 하는 데 필요한 권한이 있어야 합니다.

- Microsoft Azure에서 키에 액세스 하는 데 필요한 권한이 있어야 합니다.

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>HYOK를 사용 하 여 보호 되는 문서는 어떻게 되나요?

이중 암호화 배포는 기존 HYOK 설정에 영향을 주지 않습니다. 그러나 HYOK와 동시에 이중 암호화 사용을 시작 하는 것이 좋습니다.

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>비 Microsoft air-gapped 환경에서 이중 암호화를 실행할 수 있나요?

서비스에 Microsoft Azure에 대 한 액세스 권한이 필요 하기 때문에 DKE는 이러한 환경을 지원 하지 않습니다.

## <a name="where-can-i-store-double-key-encrypted-documents"></a>이중 키 암호화 문서를 저장할 수 있는 위치

이중 암호화 된 문서를 온-프레미스에 또는 클라우드에서 저장할 수 있습니다. 클라우드에서 암호화 된 콘텐츠를 SharePoint Online 및 비즈니스용 OneDrive로 이동할 수 있습니다. Microsoft는 개인 키에 액세스할 수 없기 때문에 암호화 된 데이터는 Microsoft에 불투명 하 게 유지 됩니다. 이는 또한 Office Web Apps에서 암호화 된 문서를 온라인에서 확인할 수 없음을 의미 합니다.

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>이중 키 암호화를 사용할 수 있는 지역 및 언어는 무엇입니까? 이중 키 암호화가 전세계적으로 사용 됩니까?

DKE 레이블은 Microsoft Information Protection의 다른 민감도 레이블과 동일한 언어로 지역화 됩니다. 이중 키 암호화는 전 세계에서 사용할 수 있습니다.

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>비 DKE 레이블을 DKE 레이블로 변환할 수 있나요?

아니요. 레이블을 만든 후에는 레이블에 DKE를 추가할 수 없습니다. 대신 **이중 키 암호화 사용** 을 선택 하 고 레이블을 만들 때 이중 키 암호화 서비스의 URL을 제공 해야 합니다.

## <a name="how-do-i-roll-my-dke-keys"></a>DKE 키를 롤 포워드 하려면 어떻게 해야 합니까?

Azure에 저장 하는 키가 롤링 (순환 또는 키 재입력이 라고도 함)에 대 한 지침은 [Azure Information Protection 테 넌 트 키에 대 한 작업](https://docs.microsoft.com/azure/information-protection/operations-customer-managed-tenant-key)을 참조 하세요.

DKE 서비스용 새 키를 만드는 방법에 대 한 자세한 내용은 [테 넌 트 및 키 설정을](double-key-encryption.md#tenant-and-key-settings) 참조 하십시오.

키를 만들 때 이름과 GUID를 설정 합니다. 그런 다음 키를 회전 하는 경우 이전 레코드를 이름 및 GUID로 유지 하지만 이름은 같지만 GUID가 다른 새 레코드를 추가 합니다. 새 키를 활성으로 설정 하 여 공개 키 API가 새 암호화를 위해이를 반환 하기 시작 합니다. 두 키를 모두 암호 해독에 사용 하 여 새 콘텐츠 및 오래 된 콘텐츠를 해독할 수 있습니다.
