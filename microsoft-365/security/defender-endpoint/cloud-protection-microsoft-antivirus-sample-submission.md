---
title: 클라우드 보호 및 샘플 제출(Microsoft Defender 바이러스 백신
description: 클라우드 제공 보호 및 보호에 대해 Microsoft Defender 바이러스 백신
keywords: Microsoft Defender 바이러스 백신, 차세대 기술, 바이러스 백신 샘플 제출, 차세대 av, 기계 학습, 맬웨어 방지, 보안, defender, 클라우드, 클라우드 제공 보호
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.date: 10/05/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: ffb8ccb40a6fcbe90d8dd0636402f8e9a40f058b
ms.sourcegitcommit: 166bf635c0905ae12c04b1865cb17aadef81e82a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2021
ms.locfileid: "60245782"
---
# <a name="cloud-protection-and-sample-submission-in-microsoft-defender-antivirus"></a>클라우드 보호 및 샘플 제출(Microsoft Defender 바이러스 백신

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)
- [Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-windows.md)

Microsoft Defender 바이러스 백신 맬웨어를 검색하는 데는 여러 가지 지능형 메커니즘이 사용되었습니다. 가장 강력한 기능 중 하나는 클라우드의 기능을 적용하여 맬웨어를 감지하고 신속한 분석을 수행하는 기능입니다. 클라우드 보호 및 자동 샘플 제출은 새로운 위협으로부터 Microsoft Defender 바이러스 백신 보호하는 데 도움이 됩니다. 

의심스러운 파일 또는 악성 파일이 감지되면 파일을 차단하는 동안 분석을 위해 샘플이 Microsoft Defender 바이러스 백신 전송됩니다. 결정이 진행되는 즉시 파일이 릴리스되거나 파일 차단에 의해 Microsoft Defender 바이러스 백신. 

이 문서에서는 클라우드 보호 및 자동 샘플 제출에 대한 개요를 Microsoft Defender 바이러스 백신. 클라우드 보호에 대한 자세한 내용은 클라우드 보호 및 클라우드 [보호를 Microsoft Defender 바이러스 백신.](cloud-protection-microsoft-defender-antivirus.md)

## <a name="how-cloud-protection-and-sample-submission-work-together"></a>클라우드 보호 및 샘플 제출이 함께 작동 하는 방법

클라우드 보호가 샘플 제출과 함께 작동하는 방법을 이해하기 위해 Endpoint용 Defender가 위협으로부터 보호하는 방법을 이해하는 데 도움이 될 수 있습니다. Microsoft 지능형 Graph 네트워크의 위협 데이터를 모니터링합니다. Microsoft는 지능형 보안 솔루션의 방대한 센서 및 데이터 네트워크와 클라이언트의 신호에 따라 파일을 평가할 수 있는 클라우드 기반 기계 학습 모델을 Graph. 이 접근 방식을 통해 끝점에 대한 Defender는 전에 볼 수 없는 여러 위협을 차단할 수 있습니다. 

다음 이미지는 클라우드 보호 및 샘플 제출의 흐름을 Microsoft Defender 바이러스 백신.

:::image type="content" source="images/cloud-protection-flow.png" alt-text="클라우드 제공 보호 흐름":::

Microsoft Defender 바이러스 백신 및 클라우드 보호는 다음 방법을 사용하여 처음에는 볼 수 없는 가장 새로운 위협을 자동으로 차단합니다.

1. 새 맬웨어 및 알 수 없는 맬웨어를 차단하는 경량 클라이언트 기반 기계 학습 모델입니다.

2. 로컬 동작 분석, 파일 기반 및 파일 비포일 공격 중지

3. 일반 및 지론 기술을 통해 일반적인 맬웨어를 감지하는 고정밀 바이러스 백신입니다.

4. 고급 클라우드 기반 보호는 끝점에서 실행되는 Microsoft Defender 바이러스 백신 의심스러운 파일의 의도를 확인하기 위해 더 많은 인텔리전스가 필요한 경우에 제공됩니다.

   1. 이 Microsoft Defender 바이러스 백신 명확한 결정이 없는 경우 파일 메타데이터가 클라우드 보호 서비스로 전송됩니다. 종종 클라우드 보호 서비스는 파일이 악성인지 아니면 위협이 아닌지 메타데이터에 따라 결정할 수 있습니다.  

      - 파일 메타데이터의 클라우드 쿼리는 동작, 웹 표시 또는 명확한 결과가 결정되지 않은 기타 특성의 결과일 수 있습니다.
      - 맬웨어의 판정에 도달하거나 위협이 아닌 목표에 도달하기 위해 작은 메타데이터 페이로드가 전송됩니다. 메타데이터에는 PII(개인 식별이 가능한 정보)가 포함되어 있지 않습니다. 파일 이름과 같은 정보는 해시됩니다.
      - 동기식 또는 비동기식일 수 있습니다. 동기식의 경우 클라우드에서 판정을 렌더링할 때까지 파일이 열립니다. 비동기의 경우 클라우드 보호가 분석을 수행하는 동안 파일이 열립니다.
      - 메타데이터에는 PE 특성, 정적 파일 특성, 동적 및 상황적 특성 등을 포함할 [수 있습니다(클라우드](#examples-of-metadata-sent-to-the-cloud-protection-service)보호 서비스로 전송된 메타데이터의 예 참조).

   2. 메타데이터를 검사한 후 Microsoft Defender 바이러스 백신 클라우드 보호가 결론에 도달할 수 없는 경우 추가 검사를 위해 파일의 샘플을 요청할 수 있습니다. 이 요청은 샘플 제출에 대한 설정 구성을 존중합니다.

      1. **안전한 샘플 자동 보내기(기본값)**
         - 금고 샘플은 일반적으로 PII 데이터를 포함하지 않는 것으로 간주되는 샘플로, .bat, .scr, .dll, .exe.
         - 파일에 PII가 포함될 가능성이 있는 경우 사용자는 파일 샘플 제출을 허용하도록 요청합니다.
         - 이 옵션은 Windows, macOS 및 Linux에서 기본값입니다.

      2. **항상 프롬프트**
         - 구성된 경우 파일 제출 전에 항상 사용자에게 동의를 요청하라는 메시지가 표시됩니다.
         - MacOS 클라우드 보호에서는 이 설정을 사용할 수 없습니다.

      3. **모든 샘플 자동 보내기**
         - 구성된 경우 모든 샘플이 자동으로 전송됩니다.
         - Word docs에 포함된 매크로를 샘플 제출에 포함하려면 "모든 샘플을 자동으로 보내기"를 선택해야 합니다.
         - MacOS 클라우드 보호에서는 이 설정을 사용할 수 없습니다.

      4. **보내지 않습니다.**
         - 파일 샘플 분석을 기반으로 "모든 시 차단"을 방지합니다.
         - "보내지 않습니다."는 macOS 정책의 "사용 안 하게" 설정과 동일합니다.
         - 샘플 제출을 사용하지 않도록 설정한 경우에도 검색을 위해 메타데이터가 전송됩니다.

   3. 메타데이터 및/또는 파일이 클라우드 보호에 제출된 후  **샘플,** 데토네이터 또는 빅 데이터 분석 기계 학습 모델을 사용하여 판정에 도달할 수 있습니다.  클라우드 제공 보호 기능을 해제하면 클라이언트가 로컬 기계 학습 모델 및 유사한 기능을 통해 제공할 수 있는 기능으로만 분석이 제한됩니다.

> [!IMPORTANT]
> [BAFS(최초](configure-block-at-first-sight-microsoft-defender-antivirus.md) 차단)는 파일 또는 프로세스가 안전한지 여부를 확인할 수 있는 발신 및 분석을 제공합니다. BAFS는 판정에 도달할 때까지 파일을 잠시 지연할 수 있습니다. 샘플 제출을 사용하지 않도록 설정하면 BAFS도 사용하지 않도록 설정되어 있으며 파일 분석은 메타데이터로만 제한됩니다. 샘플 제출 및 BAFS를 사용하도록 설정한 채로 유지하는 것이 좋습니다. 자세한 내용은 ["최초 차단"이란?을 참조하세요.](configure-block-at-first-sight-microsoft-defender-antivirus.md#what-is-block-at-first-sight)

## <a name="cloud-protection-levels"></a>클라우드 보호 수준

클라우드 보호는 기본적으로 클라우드 보호에서 Microsoft Defender 바이러스 백신. 조직의 보호 수준을 구성할 수 있는 경우 클라우드 보호를 사용하도록 설정하는 것이 좋습니다. 에 대한 클라우드 제공 보호 [수준 지정을 Microsoft Defender 바이러스 백신.](specify-cloud-protection-level-microsoft-defender-antivirus.md)

## <a name="sample-submission-settings"></a>샘플 제출 설정

클라우드 보호 수준을 구성하는 것 외에도 샘플 제출 설정을 구성할 수 있습니다. 다음과 같은 여러 옵션 중 선택할 수 있습니다.

- **안전한 샘플 자동 보내기(기본**  동작)
- **모든 샘플 자동 보내기**  
- **샘플을 보내지 않습니다.**  

Intune, Configuration Manager, GPO 또는 PowerShell을 사용하는 구성 옵션에 대한 자세한 내용은 에서 클라우드 보호 [Microsoft Defender 바이러스 백신.](enable-cloud-protection-microsoft-defender-antivirus.md)

## <a name="examples-of-metadata-sent-to-the-cloud-protection-service"></a>클라우드 보호 서비스로 전송된 메타데이터의 예

:::image type="content" source="images/cloud-protection-metadata-sample.png" alt-text="Microsoft Defender 클라우드 보호로 전송된 메타데이터의 예를 설명하는 이미지":::

다음 표에는 클라우드 보호에서 분석을 위해 전송된 메타데이터의 예가 나열됩니다.

| 유형 | 특성 |
|:---|:---|
| 컴퓨터 특성 | `OS version` <br/> `Processor` <br/> `Security settings` |
| 동적 및 상황적 특성 | **프로세스 및 설치** <br/> `ProcessName` <br/> `ParentProcess` <br/> `TriggeringSignature` <br/> `TriggeringFile` <br/> `Download IP and url` <br/> `HashedFullPath` <br/> `Vpath` <br/> `RealPath` <br/> `Parent/child relationships` <br/><br/>**동작** <br/> `Connection IPs` <br/> `System changes` <br/> `API calls` <br/> `Process injection` <br/><br/>**Locale** <br/> `Locale setting` <br/> `Geographical location` |
| 정적 파일 특성 | **부분 해시 및 전체 해시** <br/> `ClusterHash` <br/> `Crc16` <br/> `Ctph` <br/> `ExtendedKcrcs` <br/> `ImpHash` <br/> `Kcrc3n` <br/> `Lshash` <br/> `LsHashs` <br/> `PartialCrc1` <br/> `PartialCrc2` <br/> `PartialCrc3` <br/> `Sha1` <br/> `Sha256` <br/><br/>**파일 속성** <br/>`FileName` <br/> `FileSize` <br/><br/> **서명자 정보** <br/> `AuthentiCodeHash` <br/> `Issuer` <br/> `IssuerHash` <br/> `Publisher` <br/> `Signer` <br/> `SignerHash` |

## <a name="samples-are-treated-as-customer-data"></a>샘플은 고객 데이터로 처리됩니다.

샘플 제출이 진행되는 상황이 궁금할 경우 Endpoint용 Defender는 모든 파일 샘플을 고객 데이터로 처리합니다. Microsoft는 Endpoint용 Defender에 온보딩할 때 조직이 선택한 지리적 및 데이터 보존 선택을 모두 존중합니다. 

또한 Endpoint용 Defender는 여러 준수 인증을 획득하여 정교한 규정 준수 컨트롤 집합을 지속적으로 준수하고 있는 것으로 나타났습니다.

- ISO 27001
- ISO 27018
- SOC I, II, III
- 및 PCI

자세한 내용은 다음 리소스를 참조하세요.

- [Azure 규정 준수 제품](/azure/storage/common/storage-compliance-offerings) 
- [서비스 보안 포털](https://servicetrust.microsoft.com)
- [끝점 데이터 저장소 및 개인 정보 보호를 위한 Microsoft Defender](data-storage-privacy.md#data-storage-location)

## <a name="other-file-sample-submission-scenarios"></a>기타 파일 샘플 제출 시나리오

끝점용 Defender에서 클라우드 보호와 관련이 없는 파일 샘플을 요청할 수 있는 두 가지 시나리오가 Microsoft Defender 바이러스 백신. 이러한 시나리오에 대한 설명은 다음 표에 설명되어 있습니다.

| 시나리오 | 설명 |
|:---|:---|
|사이트 포털의 수동 파일 Microsoft 365 Defender 컬렉션 | 끝점용 Defender에 장치를 온보딩할 때 끝점 검색 및 응답(2016년 1월)에 대한 [설정을 구성할 EDR.](overview-endpoint-detection-response.md) 예를 들어 장치에서 샘플 컬렉션을 사용하도록 설정하는 설정이 있습니다. 이 문서에 설명된 샘플 제출 설정과 쉽게 혼동될 수 있습니다. <br/><br/>이 EDR 설정은 Microsoft 365 Defender 포털을 통해 요청될 때 장치에서 파일 샘플 컬렉션을 제어하며 이미 설정한 역할 및 사용 권한의 적용을 하게 됩니다. 이 설정은 웹 사이트 포털에서 심층 분석과 같은 기능을 위해 끝점에서 파일 수집을 허용하거나 차단할 Microsoft 365 Defender 있습니다. 이 설정이 구성되지 않은 경우 기본값은 샘플 수집을 사용하도록 설정하는 것입니다. <br/><br/>끝점 구성 설정에 대한 Defender에 대한 자세한 내용은 [Endpoint용 Defender의](configure-endpoints.md) Windows 10 도구 및 방법을 참조하세요. |
| 자동화된 조사 및 응답 콘텐츠 분석 | 장치에서 [](automated-investigations.md) 자동화된 조사가 실행되는 경우(경고 또는 수동으로 실행에 응답하여 자동으로 실행하도록 구성된 경우), 의심스러운 것으로 확인된 파일은 추가 검사를 위해 끝점에서 수집될 수 있습니다. 필요한 경우 자동화된 조사를 위한 파일 콘텐츠 분석 기능을 사이트 포털에서 사용하지 않도록 Microsoft 365 Defender 있습니다. <br/><br/> 자동화된 조사 중에 자동으로 제출되는 다른 파일 형식의 확장명을 추가하거나 제거하기 위해 파일 확장명 이름을 수정할 수도 있습니다. <br/><br/> 자세한 내용은 자동화 파일 [업로드 관리를 참조합니다.](manage-automation-file-uploads.md) |

## <a name="see-also"></a>참고 항목

[차세대 보호 개요](next-generation-protection.md)
