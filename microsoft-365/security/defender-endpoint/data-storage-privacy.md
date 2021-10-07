---
title: 끝점 데이터 저장소 및 개인 정보 보호를 위한 Microsoft Defender
description: 끝점용 Microsoft Defender가 수집하는 개인 정보 및 데이터를 처리하는 방법에 대해 자세히 알아보습니다.
keywords: 끝점용 Microsoft Defender, 데이터 저장소 및 개인 정보, 저장, 개인 정보, 라이선싱, 지리적 위치, 데이터 보존, 데이터
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a435dc0f0fb1858edcc86291c0c4c7b5ef7c565f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60166555"
---
# <a name="microsoft-defender-for-endpoint-data-storage-and-privacy"></a>끝점 데이터 저장소 및 개인 정보 보호를 위한 Microsoft Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

이 섹션에서는 끝점용 Defender의 개인 정보 및 데이터 처리와 관련하여 자주 묻는 몇 가지 질문에 대해 설명합니다.

> [!NOTE]
> 이 문서에서는 끝점용 Defender와 관련된 데이터 저장소 및 개인 정보 보호 세부 정보를 설명합니다. Endpoint용 Defender 및 Microsoft Defender 바이러스 백신 및 Windows Microsoft 개인 정보 취급 방침을 [참조하세요.](https://go.microsoft.com/fwlink/?linkid=827576) 자세한 내용은 Windows [개인 정보 FAQ도](https://go.microsoft.com/fwlink/?linkid=827577) 참조하세요.

## <a name="what-data-does-microsoft-defender-for-endpoint-collect"></a>Endpoint용 Microsoft Defender는 어떤 데이터를 수집하나요?

끝점용 Microsoft Defender는 관리, 추적 및 보고를 위한 서비스 전용 테넌트 및 고객 전용 테넌트에서 구성된 디바이스의 정보를 수집하고 저장합니다.

수집된 정보에는 파일 데이터(예: 파일 이름, 크기 및 해시), 프로세스 데이터(실행 중인 프로세스, 해시), 레지스트리 데이터, 네트워크 연결 데이터(호스트 IP 및 포트) 및 장치 세부 정보(예: 장치 식별자, 이름 및 운영 체제 버전)가 포함됩니다.

Microsoft는 이 데이터를 안전하게 Microsoft Azure Microsoft 개인 정보 취급 방침 및 Microsoft 보안 센터 정책에 따라 [유지 관리합니다.](https://go.microsoft.com/fwlink/?linkid=827578)

이 데이터는 끝점에 대한 Defender를 사용하여:

- 조직에서 IOAS(공격 지표)를 사전 식별
- 가능한 공격이 감지된 경우 경고 생성
- 네트워크의 위협 신호와 관련된 장치, 파일 및 URL에 대한 보기를 보안 운영에 제공하면 네트워크의 보안 위협 유무를 조사하고 탐색할 수 있습니다.

Microsoft는 광고를 위해 데이터를 사용하지 않습니다.

## <a name="data-protection-and-encryption"></a>데이터 보호 및 암호화

Endpoint용 Defender 서비스는 네트워크 인프라를 기반으로 하는 최첨단 데이터 보호 Microsoft Azure 활용합니다.

서비스에서 처리되는 데이터 보호와 관련된 다양한 측면이 있습니다. 암호화는 가장 중요하며 보관된 데이터 암호화, 작업 중 암호화 및 Key Vault를 사용하는 키 관리를 포함합니다. Endpoint 서비스용 Defender에서 사용하는 다른 기술에 대한 자세한 내용은 [Azure 암호화 개요를 참조하세요.](/azure/security/security-azure-encryption-overview)

모든 시나리오에서 데이터는 최소한 256비트 [AES](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) 암호화를 사용하여 암호화됩니다.

## <a name="data-storage-location"></a>데이터 저장소 위치

Endpoint용 Defender는 유럽 연합Microsoft Azure 영국 또는 미국의 데이터 센터에서 운영됩니다. 서비스에 의해 수집된 고객 데이터는 다음에 저장될 수 있습니다. (a) 프로비전 중에 식별된 테넌트의 지리적 위치 또는 (b) Endpoint용 Defender가 다른 Microsoft 온라인 서비스를 사용하여 해당 데이터를 처리한 경우, 다른 온라인 서비스의 데이터 저장소 규칙에 정의된 지리적 위치

가명 처리 양식의 고객 데이터는 미국의 중앙 저장소 및 처리 시스템에도 저장될 수 있습니다.

일단 구성되면 데이터가 저장되는 위치를 변경할 수 없습니다. 이렇게 하면 데이터가 있는 지리적 위치를 적극적으로 선택하여 규정 준수 위험을 최소화할 수 있습니다.

## <a name="is-my-data-isolated-from-other-customer-data"></a>내 데이터가 다른 고객 데이터와 격리되어 있습니까?

예. 데이터는 고객 식별자를 기반으로 하는 논리적 분리 및 액세스 인증을 통해 격리됩니다. 각 고객은 자체 조직에서 수집된 데이터와 Microsoft에서 제공하는 일반 데이터만 액세스할 수 있습니다.

## <a name="how-does-microsoft-prevent-malicious-insider-activities-and-abuse-of-high-privilege-roles"></a>Microsoft는 악의적인 내부자 활동과 높은 권한 역할 남용을 어떻게 방지하나요?

Microsoft 개발자와 관리자는 서비스 운영 및 발전을 위해 할당된 업무를 수행하기에 충분한 권한을 기본적으로 부여했습니다. Microsoft는 권한이 없는 개발자 및/또는 관리 활동으로부터 보호하기 위해 다음과 같은 메커니즘을 포함하여 예방, 감지 및 사후 제어 조합을 배포합니다.

- 중요한 데이터에 대한 엄격한 액세스 제어
- 악의적인 활동의 독립적인 감지를 크게 향상시키는 컨트롤 조합
- 여러 수준의 모니터링, 로깅 및 보고

또한 Microsoft는 특정 운영 담당자에 대한 백그라운드 확인 검사를 수행하고 백그라운드 확인 수준에 비례하여 응용 프로그램, 시스템 및 네트워크 인프라에 대한 액세스를 제한합니다. 운영 담당자는 업무 수행 시 고객의 계정 또는 관련 정보에 액세스해야 할 때 공식적인 프로세스를 따르게 됩니다.

Microsoft Azure 정부 데이터 센터에 배포된 서비스에 대한 데이터에 대한 액세스는 FedRAMP, NIST 800.171(DIB), ITAR, IRS 1075, DoD L4 및 CJIS와 같은 특정 정부 규정 및 요구 사항을 준수하는 데이터를 처리하기 위해 승인된 운영 직원에게만 부여됩니다.

## <a name="is-data-shared-with-other-customers"></a>데이터가 다른 고객과 공유하나요?

아니요. 고객 데이터는 다른 고객과 격리되어 공유되지 않습니다. 그러나 Microsoft 처리로 인한 데이터 및 고객별 데이터를 포함하지 않는 데이터에 대한 인사이트를 다른 고객과 공유할 수 있습니다. 각 고객은 자체 조직에서 수집된 데이터와 Microsoft에서 제공하는 일반 데이터만 액세스할 수 있습니다.

## <a name="how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy"></a>Microsoft에서 내 데이터를 얼마나 오래 저장하나요? Microsoft의 데이터 보존 정책이란?

### <a name="at-service-onboarding"></a>At service onboarding

기본적으로 데이터는 180일 동안 보존됩니다. 그러나 데이터에 대한 데이터 보존 정책을 지정할 수 있습니다. 이렇게 하면 끝점용 Window Defender에서 데이터를 저장할 기간이 결정됩니다. 회사의 규정 준수 요구를 충족하기 위해 1개월에서 6개월까지 유연하게 선택할 수 있습니다.

### <a name="at-contract-termination-or-expiration"></a>계약 종료 또는 만료 시

라이선스가 유예 기간 또는 일시 중단 모드에 있는 동안에는 데이터가 보관된 후 사용할 수 있습니다. 이 기간이 끝나면 계약 종료 또는 만료일로부터 180일이 지워지기 전까지 해당 데이터가 Microsoft 시스템에서 지워지기 때문에 데이터를 읽을 수 없습니다.

### <a name="advanced-hunting-data"></a>고급 헌팅 데이터

고급 헌팅은 최대 30일간의 원시 데이터를 탐색할 수 있는 쿼리 기반의 위협 헌팅 도구입니다.

## <a name="can-microsoft-help-us-maintain-regulatory-compliance"></a>Microsoft가 규정 준수를 유지 관리하는 데 도움을 줄 수 있나요?

Microsoft는 고객에게 감사 보고서 및 규정 준수 패키지를 포함하여 Microsoft의 보안 및 규정 준수 프로그램에 대한 자세한 정보를 고객에게 제공하여 고객이 자신의 법적 및 규정 요구 사항에 따라 끝점 서비스에 대한 Defender를 평가하는 데 도움을 줄 수 있습니다. Endpoint용 Defender는 ISO, SOC, FedRAMP High 및 PCI를 비롯한 다양한 인증을 획득하고 추가 국가, 지역 및 산업별 인증을 계속 진행하고 있습니다.

고객에게 독립적으로 검증된 규정 준수 서비스를 제공하여 Microsoft는 고객이 실행하는 인프라 및 응용 프로그램에 대한 규정 준수를 더 쉽게 달성할 수 있도록 합니다.

Endpoint용 Defender 인증 보고서에 대한 자세한 내용은 [Microsoft 보안 센터를 참조하세요.](https://servicetrust.microsoft.com/) 

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-datastorage-belowfoldlink)
