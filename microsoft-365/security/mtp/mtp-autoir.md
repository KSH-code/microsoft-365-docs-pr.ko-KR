---
title: Microsoft Threat Protection의 자동화된 조사 및 대응
description: Microsoft Threat Protection의 자동화된 조사 및 대응 기능에 대한 개요를 확인하세요.
keywords: 자동화된, 조사, 경고, 트리거, 작업, 수정
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 8c82c00bb785086da424072581252e6085937921
ms.sourcegitcommit: 8c244b38c43dd00c4ef0102f8bed02ab36639a6b
ms.translationtype: MT + HT Review
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "39967911"
---
# <a name="automated-investigation-and-response-air-in-microsoft-threat-protection"></a>Microsoft Threat Protection의 자동화된 조사 및 대응(AIR)

**적용 대상:**
- Microsoft Threat Protection

[!include[Prerelease information](prerelease.md)]

## <a name="your-virtual-analyst"></a>가상 분석가

보안 경고가 트리거되면 보안 운영팀이 해당 경고를 살펴보고 조직 보호 단계를 수행해야 합니다. 조사가 진행되는 동안 새 경고를 계속해서 받는 경우 경고 우선 순위를 설정하고 검사하는 것은 매우 시간이 오래 걸릴 수 있습니다. 보안 운영 팀은 모니터링하고 방어해야 하는 많은 위협 요소를 통해 압도될 수 있습니다. 

계층 1/계층 2 보안 운영팀에 가상 분석가가 있다고 가정합니다. 가상 분석가가 보안 운영에서 위협을 조사하고 수정하는 데 취하는 이상적인 단계를 모방합니다. 가상 도우미는 연중무휴, 무제한으로 작업하고, 상당한 양의 조사와 위협 수정을 수행할 수 있습니다. 이러한 가상 도우미는 대응 시간을 크게 줄이고 보안 운영팀이 다른 중요한 전략 프로젝트를 수행할 수 있도록 합니다. 이 시나리오가 공상 과학 소설 같이 들린다면 그렇지 않습니다! 이러한 가상 분석가는 Microsoft Threat Protection 제품군의 일부이며, 이름은 *자동화된 조사와 대응*(AIR)입니다.

AIR을 사용하면 보안 운영팀에서 보안 경고와 인시던트를 처리하는 조직의 용량을 획기적으로 늘릴 수 있습니다. AIR을 사용하여 조사 및 수정 활동을 처리하는 비용을 줄이고 위협 방지 제품군을 최대한 활용할 수 있습니다. AIR은 다음과 같은 방법으로 보안 운영팀에게 도움을 줍니다.

1.  위협이 조치를 요구하는지 여부 확인
2.  필수 수정 조치 수행(또는 권장)
3.  어떤 추가 조사가 수행되어야 하는지 결정
4.  다른 경고가 발생하면 필요한 프로세스를 반복

## <a name="the-automated-investigation-process"></a>자동화된 조사 프로세스

**경고** > **인시던트** > **자동화된 조사** > **판단** > **수정 작업**

개략적으로 트리거되는 경고는 자동화된 조사를 시작할 수 있는 인시던트를 생성합니다. 이 조사를 수행하면 하나 이상의 수정 작업이 발생할 수 있습니다. 다음 표에 요약된대로 Microsoft Threat Protection에서 각각의 자동화된 조사는 Azure ATP(Advanced Threat Protection), Microsoft Defender online(Microsoft Defender ATP) 및 Office 365 Advanced Threat Protection(Office 365 ATP)간 신호의 연관성을 보여줍니다. 

|엔터티 |위협 보호 서비스  |
|---------|---------|
|장치(끝점이라고도 함)     |[Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)<br/>[Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) |      
|전자 메일 콘텐츠(사서함의 파일 및 메시지)     |[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)         |


각 조사는 조사된 각 증거에 대한 판정(*악성*, *의심* 또는 *깨끗*)을 생성합니다. 위협 유형과 결과 판정에 따라 수정 작업이 자동으로 수행되거나 조직의 보안 운영 팀의 승인에 따라 발생합니다. 보류 중인 동작과 완료된 작업은 [알림 센터](mtp-action-center.md)에 나열되어 있습니다.

조사가 실행되는 동안 발생하는 모든 관련 경고는 완료될 때까지 조사에 추가됩니다. 문제가 있는 엔터티가 다른 곳에서 발견되는 경우에는 자동화된 조사가 해당 엔터티를 포함하도록 범위를 확장하고 일반적인 보안 플레이 북이 실행됩니다. 

> [!NOTE]
> 모든 경고가 자동 조사를 트리거하는 것이 아니고 모든 조사로 자동화된 수정 작업이 수행되지 않습니다. 이는 조직에 AIR이 구성되는 방식에 따라 달라집니다. 

## <a name="requirements-for-air-in-microsoft-threat-protection"></a>Microsoft Threat Protection의 AIR에 대한 요구 사항

| | |
|--|--|
|구독 요구 사항 |- ID 및 위협 방지가 있는 Microsoft 365 E5 또는 Microsoft 365 E3<br/>= [Microsoft 365 요금제](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-overview#plans) 참조|
|네트워크 요구 사항 |- [Azure ATP](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp) 사용<br/>- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)(MCAS) 구성됨<br/>- [Azure ATP와 통합된 MCAS](https://docs.microsoft.com/cloud-app-security/aatp-integration) |
|Windows 컴퓨터 요구 사항 |- Windows 10, 버전 1709 이상이 설치됨([Windows 10 릴리스 정보](https://docs.microsoft.com/windows/release-information/)참조)<br/>- [Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) 구성됨 <br/>- [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) 구성됨 |
|사용 권한 |- AIR을 *구성*하려면 Azure Active Directory([https://portal.azure.com](https://portal.azure.com)) 또는 Microsoft 365 관리 센터([https://admin.microsoft.com](https://admin.microsoft.com))에 할당된 **전역 관리자** 또는 **보안 관리자** 역할이 있어야 합니다.<br/><br/>- AIR 기능을 *사용*하려면 [알림 센터 작업에 필요한 사용 권한](mtp-action-center.md#required-permissions-for-action-center-tasks)을 참조하세요. |

## <a name="next-steps"></a>다음 단계

- [자동화된 조사 및 대응과 관련된 조치 승인 또는 거부](mtp-autoir-actions.md)
- [알림 센터에 대한 자세한 정보](mtp-action-center.md)
