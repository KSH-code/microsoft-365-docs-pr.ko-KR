---
title: 이중 키 암호화 개요 및 FAQ
description: 이중 키 암호화에 대한 질문과 Microsoft 365.
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 12/11/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: ed07361f8c433a318342ae3c8ad750549992c285
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59212665"
---
# <a name="double-key-encryption-frequently-asked-questions"></a>이중 키 암호화 자주 묻는 질문

이중 키 암호화의 작동 방식에 대한 질문이 있나요? 여기에서 답변을 확인하세요.

## <a name="what-is-double-key-encryption-for-microsoft-365-dke"></a>DKE(Double Key Encryption)Microsoft 365 암호란?

고객용 이중 Microsoft 365 암호화를 통해 고객은 특수한 요구 사항을 충족하기 위해 매우 중요한 데이터를 보호할 수 있습니다. 이는 고객이 암호화 키에 대한 모든 제어를 유지하는 데 도움이 됩니다. 두 키를 사용하여 데이터를 보호합니다. 컨트롤의 키 하나와 두 번째 키는 컨트롤에 안전하게 Microsoft Azure. 이중 키 암호화로 보호된 데이터를 보는 경우 두 키에 모두 액세스해야 합니다. Microsoft는 이러한 키 중 하나에만 액세스할 수 있으며 보호된 데이터는 Microsoft에 액세스할 수 없는 상태로 유지하여 데이터 개인 정보 및 보안을 완전하게 제어할 수 있도록 합니다.  

원하는 위치(사내 키 관리 서버 또는 클라우드)에서 키를 요청하는 데 사용되는 이중 키 암호화 서비스를 호스팅할 수 있습니다. 다른 응용 프로그램과 같은 서비스도 유지 관리합니다. 이중 키 암호화를 사용하면 이중 키 암호화 서비스에 대한 액세스를 제어할 수 있습니다. 매우 중요한 데이터를 사내에 저장하거나 클라우드로 이동할 수 있습니다. 키에 대한 모든 권한을 유지 관리하기 때문에 타사 액세스를 방지할 수 있습니다. 이중 키 암호화를 사용하면 데이터와 키를 같은 위치에 저장할 수 있습니다.

DKE를 사용하면 GDPR(일반 데이터 보호 규정), HIPAA(Health Insurance Portability and Accountability Act), GLBA(Gramm-Leach-Bliley Act), 러시아의 데이터 지역화 법률 - 연방법 No와 같은 여러 규정 및 표준에 대한 규정 요구 사항을 충족할 수 있습니다. 242-FZ, 오스트레일리아 연방 개인 정보 보호법 1988 및 뉴질랜드 개인 정보 보호법 1993.

## <a name="can-i-use-double-key-encryption-with-microsoft-office-built-in-sensitivity-labeling"></a>기본 제공 민감도 레이블 Microsoft Office 이중 키 암호화를 사용할 수 있나요?

Azure Information Protection 통합 레이블 지정 클라이언트를 사용하여 이중 키 암호화로 문서를 보호해야 합니다. 현재는 기본 제공 민감도 Microsoft Office 사용할 수 없습니다.

## <a name="what-microsoft-365-apps-can-i-use-with-dke"></a>DKE에서 Microsoft 365 앱 수 있는 방법

DKE 레이블을 사용하여 데스크톱 버전의 Word, Excel 및 PowerPoint 사용하여 문서를 Windows. 이 버전에서 *.12711 이상(데스크톱 버전의 Word, PowerPoint 및 Excel)을 사용하고 Windows.

## <a name="how-is-double-key-encryption-different-from-the-existing-hold-your-own-key-hyok-solution"></a>이중 키 암호화는 기존에 보유한 키(HYOK) 솔루션과 어떻게 다른가요?

이중 키 암호화는 두 개의 키로 데이터를 암호화합니다. 암호화 키가 제어에 있으며 두 번째 키는 Microsoft Azure 저장되므로 암호화된 데이터를 클라우드로 이동할 수 있습니다. HYOK는 키가 하나만 있는 콘텐츠를 보호하며 키는 항상 프레미스에 있습니다.  

## <a name="can-double-key-encrypted-documents-be-shared-externally"></a>이중 키 암호화된 문서를 외부에서 공유할 수 있나요?

다음 사용자에 한해 이중 키 암호화된 문서를 별도의 테넌트의 사용자와 공유할 수 있습니다.

- 이중 키 암호화 서비스의 키에 액세스하는 데 필요한 권한이 있습니다.

- 키에 액세스하는 데 필요한 권한이 Microsoft Azure.

## <a name="what-happens-to-documents-that-are-protected-with-hyok"></a>HYOK로 보호되는 문서는 어떻게 하나요?

이중 키 암호화를 배포하면 기존 HYOK 설정에 영향을 주지 않습니다. 그러나 HYOK와 동시에 이중 키 암호화를 사용하는 것이 좋습니다.

## <a name="can-i-run-double-key-encryption-in-my-non-microsoft-air-gapped-environment"></a>Microsoft가 아닌 Air-gapped 환경에서 이중 키 암호화를 실행할 수 있나요?

DKE는 서비스에서 해당 환경에 대한 액세스 권한이 필요하기 때문에 이러한 환경을 Microsoft Azure.

## <a name="where-can-i-store-double-key-encrypted-documents"></a>이중 키 암호화된 문서는 어디에서 저장할 수 있나요?

이중 키 암호화된 문서를 사내 또는 클라우드에 저장할 수 있습니다. 클라우드에서 암호화된 콘텐츠를 온라인 및 SharePoint 이동할 수 비즈니스용 OneDrive. Microsoft는 개인 키에 액세스할 수 없습니다. 암호화된 데이터는 Microsoft에 불투명하게 남아 있습니다. 즉, 웹앱에서 온라인으로 암호화된 문서를 볼 Office 없습니다.

## <a name="what-regions-and-languages-is-double-key-encryption-available-in-is-double-key-encryption-available-worldwide"></a>이중 키 암호화를 사용할 수 있는 지역 및 언어는 무엇입니까? 이중 키 암호화는 전 세계에 사용 가능합니까?

DKE 레이블은 다른 민감도 레이블과 동일한 언어로 지역화되어 Microsoft Information Protection. 이중 키 암호화는 전 세계적으로 사용할 수 있습니다.

## <a name="can-i-convert-a-non-dke-label-to-a-dke-label"></a>DKE가 아닌 레이블을 DKE 레이블로 변환할 수 있나요?

아니요. 만든 레이블에는 DKE를 추가할 수 없습니다. 대신 이중 키  암호화 사용을 선택하고 레이블을 만들 때 이중 키 암호화 서비스의 URL을 제공해야 합니다.

## <a name="how-do-i-roll-my-dke-keys"></a>DKE 키를 롤링하는 방법

Azure에 저장하는 키의 롤링(회전 또는 다시 키라고도 불리며)에 대한 지침은 Azure Information Protection 테넌트 키에 대한 작업을 [참조하세요.](/azure/information-protection/operations-customer-managed-tenant-key)

DKE 서비스의 새 [키를](double-key-encryption.md#tenant-and-key-settings) 만드는 데 대한 자세한 내용은 테넌트 및 키 설정을 참조하세요.

키를 만들 때 이름과 GUID를 설정할 수 있습니다. 그런 다음 키를 회전하면 이전 레코드에 이름과 GUID가 유지되지만 이름이 같지만 GUID가 다른 새 레코드를 추가합니다. 공개 키 API가 새 암호화를 위해 반환을 시작할 수 있도록 새 키가 활성으로 설정됩니다. 새 콘텐츠와 이전 콘텐츠의 암호를 해독할 수 있도록 암호 해독에 두 키를 모두 사용할 수 있습니다.