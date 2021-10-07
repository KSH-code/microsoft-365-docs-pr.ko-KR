---
title: 동작 차단 및 제약
description: 끝점용 Microsoft Defender의 동작 차단 및 포함 기능에 대해 자세히 알아보기
keywords: 끝점용 Microsoft Defender, EDR 모드, 수동 모드 차단
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.localizationpriority: medium
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: af80bd0c8c6bcfab823d3391d99c33f35d3e5557
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197032"
---
# <a name="behavioral-blocking-and-containment"></a>동작 차단 및 제약

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>개요

오늘날의 위협 환경은 파일 [](/windows/security/threat-protection/intelligence/fileless-threats) 없는 맬웨어로 오버런되고, 기존의 솔루션보다 빠르게 변이되는 매우 다형성 위협과 손상된 디바이스에서 적들이 발견하는 공격에 적응하는 인간이 운영하는 공격에 의해 해결됩니다. 기존 보안 솔루션만으로는 이러한 공격을 막을 수 없습니다. 엔드포인트용 [Defender에](/windows/security)포함된 인공 지능(AI) 및 ML(장치 학습) 지원 기능(예: 동작 차단 및 포함)이 필요합니다.

동작 차단 및 포함 기능은 위협이 실행을 시작한 경우에도 동작 및 처리 트리에 따라 위협을 식별하고 중지하는 데 도움이 될 수 있습니다. 엔드포인트 구성 요소 및 기능에 대한 차세대 보호, EDR 및 Defender는 동작 차단 및 포함 기능에서 함께 작동됩니다.

:::image type="content" source="images/mdatp-next-gen-EDR-behavblockcontain.png" alt-text="동작 차단 및 포함.":::

동작 차단 및 포함 기능은 끝점용 Defender의 여러 구성 요소 및 기능과 함께 작동하여 공격을 즉시 중지하고 공격이 진행되지 않도록 합니다.

- [차세대 보호(Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md) 포함)는 동작을 분석하여 위협을 감지하고 실행을 시작한 위협을 중지할 수 있습니다.

- [끝점 감지](overview-endpoint-detection-response.md) 및 응답(EDR)은 네트워크, 장치 및 커널 동작을 통해 보안 신호를 수신합니다. 위협이 감지되면 경고가 생성됩니다. 동일한 유형의 여러 경고가 인시던트로 집계됩니다. 따라서 보안 운영 팀이 보다 쉽게 조사하고 대응할 수 있습니다.

- [끝점용 Defender에는](overview-endpoint-detection-response.md) 네트워크, 끝점 및 커널 동작을 통해 수신된 네트워크, 끝점 및 커널 동작 신호 외에도 ID, 전자 메일, 데이터 및 앱에 걸쳐 광범위한 광학 EDR. 의 [](../defender/microsoft-365-defender.md)구성 Microsoft 365 Defender 끝점용 Defender는 이러한 신호를 처리하고, 검색 경고를 발생시킵니다. 인시던트에서 관련 경고를 연결합니다.

이러한 기능을 사용하여 실행을 시작한 경우에도 더 많은 위협을 방지하거나 차단할 수 있습니다. 의심스러운 동작이 감지될 때마다 위협이 포함되어 경고가 생성되고 추적에서 위협이 중지됩니다.

다음 이미지는 동작 차단 및 포함 기능에 의해 트리거된 경고의 예를 보여줍니다.

:::image type="content" alt-text="동작 차단 및 포함을 통한 경고의 예" source="images/blocked-behav-alert.png" lightbox="images/blocked-behav-alert.png":::

## <a name="components-of-behavioral-blocking-and-containment"></a>동작 차단 및 포함의 구성 요소

- **클라이언트에서 정책 기반 공격 [표면 감소 규칙](attack-surface-reduction.md)** 미리 정의한 일반적인 공격 동작은 공격 표면 감소 규칙에 따라 실행되지 않습니다. 이러한 동작이 실행을 시도하면 Microsoft 365 Defender 포털()에서 정보 알림으로 볼 [https://security.microsoft.com](https://security.microsoft.com) 수 있습니다. 공격 표면 감소 규칙은 기본적으로 사용되지 않습니다. Microsoft 365 Defender [포털에서 정책을 구성합니다.](microsoft-defender-security-center.md)

- **[클라이언트 동작 차단](client-behavioral-blocking.md)** 끝점의 위협은 기계 학습을 통해 감지된 다음 자동으로 차단되고 수정됩니다. 클라이언트 동작 차단은 기본적으로 사용하도록 설정됩니다.

- **[피드백 루프](feedback-loop-blocking.md)** 차단(신속한 보호라고도 지칭) 위협 감지는 동작 인텔리전스를 통해 관찰됩니다. 위협이 중지되고 다른 끝점에서 실행되지 않습니다. 피드백 루프 차단은 기본적으로 사용하도록 설정됩니다.

- **[차단 모드의 끝점 EDR 응답(EDR)](edr-in-block-mode.md)** 위반 후 보호를 통해 관찰되는 악의적인 아티팩트 또는 동작은 차단되어 포함되어 있습니다. EDR 기본 바이러스 백신 솔루션이 아니어도 Microsoft Defender 바이러스 백신 모드로 전환됩니다. (EDR 모드에서는 기본적으로 사용하도록 설정되지 않습니다. 이 설정은 Microsoft 365 Defender.

Microsoft는 계속해서 위협 방지 기능과 기능을 개선하기에 따라 동작 차단 및 포함 영역에 더 많은 것이 제공될 것으로 예상합니다. 현재 계획된 계획 및 롤아웃을 보시다시피 Microsoft 365 [로드맵을 방문하세요.](https://www.microsoft.com/microsoft-365/roadmap)

## <a name="examples-of-behavioral-blocking-and-containment-in-action"></a>동작 차단 및 실행 포함의 예

동작 차단 및 포함 기능은 다음과 같은 공격자 기술을 차단했습니다.

- LSASS에서 자격 증명 덤프
- 크로스 프로세스 주입
- 프로세스 비우기
- 사용자 계정 컨트롤 우회
- 바이러스 백신 변조(예: 바이러스 백신을 사용하지 않는 경우 또는 맬웨어를 제외로 추가)
- 명령 및 제어(C&C)에 문의하여 페이로드 다운로드
- 코인 마이너스
- 부팅 레코드 수정
- 해시 전달 공격
- 루트 인증서 설치
- 다양한 취약점에 대한 악용 시도

다음은 동작 차단 및 실행 포함의 실제 두 가지 예입니다.

### <a name="example-1-credential-theft-attack-against-100-organizations"></a>예제 1: 100개 조직에 대한 자격 증명 도난 공격

[Elusive Threats에](https://www.microsoft.com/security/blog/2019/10/08/in-hot-pursuit-of-elusive-threats-ai-driven-behavior-based-blocking-stops-attacks-in-their-tracks)설명된 바와 같이: AI 기반 동작 기반 차단은 추적에서 공격을 중지합니다. 전 세계 100개 조직에 대한 자격 증명 도난 공격은 행동 차단 및 포함 기능에 의해 중지되었습니다. 루이지 문서가 포함된 스피어 피싱 전자 메일 메시지를 대상 조직으로 전송했습니다. 받는 사람이 첨부 파일을 연 경우 관련 원격 문서가 사용자의 디바이스에서 코드를 실행하고 Lokibot 맬웨어를 로드할 수 있습니다. 이 맬웨어는 자격 증명을 훔치고 훔친 데이터를 유출하고 명령 및 제어 서버에서 추가 지침을 기다립니다.

Endpoint용 Defender의 동작 기반 장치 학습 모델은 공격 체인에서 다음 두 지점에서 공격자 기술을 잡았다가 중지했습니다.

- 첫 번째 보호 계층에서 악용 동작을 감지했습니다. 클라우드의 장치 학습 분류자는 공격을 차단하라는 지시와 함께 위협을 올바르게 식별하고 즉시 클라이언트 장치에 지시했습니다.
- 두 번째 보호 계층은 공격이 첫 번째 계층을 넘어가고, 프로세스 공백을 감지하고, 해당 프로세스를 중지하고, 해당 파일(예: Lokibot)을 제거한 경우를 중지하는 데 도움을 주었다.

공격이 감지되고 중지되는 동안 "초기 액세스 알림"과 같은 경고가 트리거되고 Microsoft 365 Defender [포털에 표시됩니다.](microsoft-defender-security-center.md)

:::image type="content" source="images/behavblockcontain-initialaccessalert.png" alt-text="사이트 포털의 초기 액세스 Microsoft 365 Defender 알림입니다.":::

이 예에서는 실행을 시작한 후에도 클라우드의 동작 기반 장치 학습 모델이 공격으로부터 새로운 보호 계층을 추가하는 방법을 보여 주며,

### <a name="example-2-ntlm-relay---juicy-potato-malware-variant"></a>예제 2: NTLM 릴레이 - Juicy Malware malware variant

최근 블로그 게시물 동작 차단 및 [포함:](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection)2020년 1월에 끝점용 Defender가 조직의 장치에서 권한 에스컬레이터 활동을 감지했습니다. "NTLM 릴레이를 사용하여 가능한 권한 에스컬레이터"라는 경고가 트리거됩니다.

:::image type="content" alt-text="Juicy Malware 맬웨어에 대한 NTLM 경고입니다." source="images/NTLMalertjuicypotato.png" lightbox="images/NTLMalertjuicypotato.png":::

위협이 맬웨어로 발견되었습니다. 이 도구는 공격자가 디바이스에서 권한 에스컬레이터를 다운로드하는 데 사용되는 주크로(Juicy)라는 의심스러운 해킹 도구의 새로운 변형으로, 볼 수 없습니다.

경고가 트리거된 후 파일이 분석된 후 악성으로 확인된 시간(분)입니다. 다음 이미지와 같이 프로세스가 중지 및 차단되었습니다.

:::image type="content" alt-text="아티팩트가 차단됩니다." source="images/Artifactblockedjuicypotato.png" lightbox="images/Artifactblockedjuicypotato.png":::

아티팩트가 차단된 후 몇 분 후에 동일한 파일의 여러 인스턴스가 동일한 장치에서 차단되어 더 많은 공격자 또는 기타 맬웨어가 디바이스에 배포되지 못하게 합니다.

이 예에서는 동작 차단 및 포함 기능을 통해 위협이 자동으로 감지, 포함 및 차단되는 것으로 보여집니다.

## <a name="next-steps"></a>다음 단계

- [끝점용 Defender에 대해 자세히 알아보시고](overview-endpoint-detection-response.md)

- [공격 표면 감소 규칙 구성](attack-surface-reduction.md)

- [차단 EDR 사용](edr-in-block-mode.md)

- [최근 전역 위협 활동 보기](https://www.microsoft.com/wdsi/threats)

- [개요를 Microsoft 365 Defender](../defender/microsoft-365-defender.md)
