---
title: 랜섬웨어 공격으로부터 복구
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Microsoft 365 관리자가 랜섬웨어 공격으로부터 복구하는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d2bb99111142be683c6504010576253784d3cd68
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60210404"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>랜섬웨어 공격으로부터 Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

조직을 보호하기 위해 모든 예방 조치를 취하는 경우에도 여전히 랜섬웨어 공격의 피해가 될 [수](/windows/security/threat-protection/intelligence/ransomware-malware) 있습니다. 랜섬웨어는 대기업이자 오늘날의 위협 환경 Microsoft 365 정교한 공격의 대상이 될 [것입니다.](https://i.blackhat.com/USA21/Wednesday-Handouts/us-21-Cloudy-With-A-Chance-Of-APT-Novel-Microsoft-365-Attacks-In-The-Wild.pdf)

이 문서의 단계는 데이터를 복구하고 내부 감염 확산을 중지할 수 있는 최상의 기회를 제공합니다. 시작하기 전에 다음 항목을 고려하세요.

- 대금을 지불하면 파일에 대한 액세스 권한이 반환된다고 보장할 수 없습니다. 실제로 대가를 지불하면 더 많은 랜섬웨어의 대상이 될 수 있습니다.

  이미 결제했지만 공격자 솔루션을 사용하지 않고 복구한 경우 은행에 문의하여 거래를 차단할 수 있는지 문의합니다.

  또한 랜섬웨어 공격을 법 집행 기관, 사기 보고 웹 사이트 및 Microsoft에 보고하는 것이 좋습니다.

- 공격과 그 결과에 신속하게 대응하는 것이 중요합니다. 대기 시간이 길면 영향을 받는 데이터를 복구할 가능성이 낮아질 수 있습니다.

## <a name="step-1-verify-your-backups"></a>1단계: 백업 확인

오프라인 백업이 있는 경우 환경에서 랜섬웨어  페이로드(맬웨어)를 제거한 후 그리고 Microsoft 365  환경에서 무단 액세스 권한이 없음을 확인한 후에 암호화된 데이터를 복원할 수 있습니다.

백업이 없는 경우 또는 백업이 랜섬웨어의 영향을 받은 경우 이 단계를 건너뛸 수 있습니다.

## <a name="step-2-disable-exchange-activesync-and-onedrive-sync"></a>2단계: Exchange ActiveSync 및 OneDrive 동기화

여기서 핵심은 랜섬웨어에 의해 데이터 암호화의 확산을 중지하는 것입니다.

전자 메일이 랜섬웨어 암호화의 대상으로 의심되는 경우 사서함에 대한 사용자 액세스를 일시적으로 사용하지 않도록 설정하십시오. Exchange ActiveSync 사서함과 장치 간에 데이터를 Exchange Online 동기화합니다.

사서함에 Exchange ActiveSync 사용하지 않도록 설정하는 방법에 대한 자세한 내용은 Exchange ActiveSync 사용자에 대해 사서함을 사용하지 않도록 설정하는 [Exchange Online.](https://support.microsoft.com/help/2795303)

다른 유형의 사서함 액세스를 사용하지 않도록 설정하는 경우 다음을 참조합니다.

- [사서함에 대해 MAPI를 사용하도록 설정하거나 사용하지 않도록 설정](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)

- [사용자에 대해 POP3 또는 IMAP4 액세스 사용 또는 사용 안 하도록 설정](/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

이 OneDrive 동기화 사용하면 잠재적으로 감염된 장치에 의해 클라우드 데이터가 업데이트되지 못하도록 보호할 수 있습니다. 자세한 내용은 에서 동기화 일시 중지 및 다시 시작 방법을 [OneDrive.](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>3단계: 영향을 받는 장치에서 맬웨어 제거

의심되는 모든 컴퓨터 및 장치에서 최신 바이러스 백신 검색을 실행하여 랜섬웨어와 연결된 페이로드를 검색하고 제거합니다.

데이터를 동기화하는 장치 또는 매핑된 네트워크 드라이브의 대상을 검색하는 것을 잊지 마세요.

에서 [Windows Defender](https://www.microsoft.com/windows/comprehensive-security) 또는 (이전 클라이언트의 [경우)](https://www.microsoft.com/download/details.aspx?id=5201)를 사용할 Microsoft Security Essentials.

랜섬웨어 또는 맬웨어를 제거하는 데 도움이 되는 [대안으로는 MSRT(악성](https://www.microsoft.com/download/details.aspx?id=9905)소프트웨어 제거 도구)가 있습니다.

이러한 옵션이 작동하지 않는 경우 오프라인으로 또는 맬웨어 [Windows Defender](https://support.microsoft.com/help/17466) 문제 해결을 시도할 [수 있습니다.](https://support.microsoft.com/help/4466982)

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>4단계: 정리된 컴퓨터 또는 장치에서 파일 복구

사용자 환경에서 랜섬웨어 페이로드를 제거하기 위한 이전 단계를 완료한 후(랜섬웨어가 파일을 암호화하거나 제거하는 것을 방지) Windows 11, Windows 10, Windows 8.1 및 Windows 7의 시스템 보호를 사용하여 로컬 파일 및 폴더를 복구할 수 있습니다. [](https://support.microsoft.com/help/17128)

**참고**:

- 일부 랜섬웨어는 또한 백업 버전을 암호화하거나 삭제하기 때문에 파일 기록 또는 시스템 보호를 사용하여 파일을 복원할 수 없습니다. 이 경우 다음 섹션에 설명된 바와 같이 랜섬웨어 또는 랜섬웨어의 영향을 받지 OneDrive 장치에서 백업을 사용해야 합니다.

- 폴더가 OneDrive 동기화되어 최신 버전의 폴더를 사용하지 않는 Windows 파일 기록을 사용하는 데 몇 가지 제한이 있을 수 있습니다.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>5단계: 사용자 설정에서 파일 비즈니스용 OneDrive

파일 비즈니스용 OneDrive 복원을 사용하면 지난 30일 OneDrive 이전 시점으로 전체 파일을 복원할 수 있습니다. 자세한 내용은 [OneDrive 복구](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)를 참조하세요.

## <a name="step-6-recover-deleted-email"></a>6단계: 삭제된 전자 메일 복구

드물지만 랜섬웨어가 모든 전자 메일을 삭제한 경우 삭제된 항목을 복구할 수 있습니다. 자세한 내용은 다음을 참조하세요.

- [사용자의 사서함에서 삭제된 메시지 복구](/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Windows용 Outlook에서 삭제된 항목 복구](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>7단계: 사용자 Exchange ActiveSync 다시 OneDrive 동기화

컴퓨터와 장치를 정리하고 데이터를 복구한 후 이전에 [2단계에서](#step-2-disable-exchange-activesync-and-onedrive-sync)사용하지 않도록 Exchange ActiveSync OneDrive 동기화 다시 사용하도록 설정할 수 있습니다.

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>8단계(선택 사항): 특정 OneDrive 동기화 확장명에 대한 차단

복구한 후 비즈니스용 OneDrive 클라이언트가 이 랜섬웨어의 영향을 받은 파일 형식을 동기화하지 못하게 할 수 있습니다. 자세한 내용은 [Set-SPOTenantSyncClientRestriction을 참조하세요.](/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>공격 보고

### <a name="contact-law-enforcement"></a>연락 사법 기관

현지 또는 연방 사법 기관에 문의해야 합니다. 예를 들어 미국에 있는 경우 [FBI](https://www.fbi.gov/contact-us/field)현지 현장 사무실, [IC3](http://www.ic3.gov/complaint/default.aspx) 또는 비밀 서비스에 [문의할 수 있습니다.](http://www.secretservice.gov/)

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>국가의 사기 보고 웹 사이트에 보고서 제출

사기 보고 웹 사이트는 사기를 방지하고 방지하는 방법에 대한 정보를 제공합니다. 또한 사기를 당했다고 보고하는 메커니즘도 제공합니다.

- 오스트레일리아: [SCAMwatch](http://www.scamwatch.gov.au/)

- 캐나다: [캐나다의 사기 방지 센터](http://www.antifraudcentre-centreantifraude.ca/)

- 프랑스: [기관 국가 de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- 독일: [Bundesamt für Sicherheit in der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- 아일랜드: [Garda Síochána](http://www.garda.ie/)

- 뉴질랜드: [소비자 업무 사기](http://www.consumeraffairs.govt.nz/scams)

- 스위스 [국가 Zentrum für Cybersicherheit NCSC](https://www.ncsc.admin.ch/ncsc/de/home.html)

- 영국: [작업 사기](http://www.actionfraud.police.uk/)

- 미국: [On Guard Online](http://www.onguardonline.gov/)

해당 국가가 목록에 없는 경우 현지 또는 연방 법 집행 기관에 요청합니다.

### <a name="submit-email-messages-to-microsoft"></a>Microsoft에 전자 메일 메시지 제출

여러 방법 중 하나를 사용하여 랜섬웨어가 포함된 피싱 메시지를 보고할 수 있습니다. 자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.

## <a name="additional-ransomware-resources"></a>추가 랜섬웨어 리소스

Microsoft의 주요 정보:

- [랜섬웨어 위협 증가](https://blogs.microsoft.com/on-the-issues/2021/07/20/the-growing-threat-of-ransomware/), 2021년 7월 20일 Microsoft On the Issue 블로그 게시물
- [사람이 조작하는 랜섬웨어](/security/compass/human-operated-ransomware)
- [랜섬웨어 및 탈취로부터 신속하게 보호](/security/compass/protect-against-ransomware)
- [최신 Microsoft 보안 인텔리전스 보고서](https://www.microsoft.com/securityinsights/)(22-24페이지 참조)
- **랜섬웨어:** Microsoft 365 Defender 포털의 **위협 분석** 노드에 만연하고 지속적인 위협 보고서가 있습니다(이 [라이선스 요구 사항](/microsoft-365/security/defender/prerequisites#licensing-requirements) 참조).

Microsoft 365:

- [Microsoft 365 테넌트용 랜섬웨어 보호 배포](/microsoft-365/solutions/ransomware-protection-microsoft-365)
- [Azure 및 랜섬웨어의 탄력성을 최대화하고 Microsoft 365](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [맬웨어 및 랜섬웨어 보호](/compliance/assurance/assurance-malware-and-ransomware-protection)
- [랜섬웨어로부터 Windows PC 보호](https://support.microsoft.com//windows/protect-your-pc-from-ransomware-08ed68a7-939f-726c-7e84-a72ba92c01c3)
- [SharePoint Online에서 랜섬웨어 처리](/sharepoint/troubleshoot/security/handling-ransomware-in-sharepoint-online)

Microsoft 365 Defender:

- [고급 헌팅으로 랜섬웨어 찾기](/microsoft-365/security/defender/advanced-hunting-find-ransomware)

Microsoft Azure:

- [랜섬웨어 공격용 Azure 방어](https://azure.microsoft.com/resources/azure-defenses-for-ransomware-attack/)
- [Azure 및 랜섬웨어의 탄력성을 최대화하고 Microsoft 365](https://azure.microsoft.com/resources/maximize-ransomware-resiliency-with-azure-and-microsoft-365/)
- [랜섬웨어로부터 보호하기 위한 백업 및 복원 계획](/security/compass/backup-plan-to-protect-against-ransomware)
- [랜섬웨어로부터](https://www.youtube.com/watch?v=VhLOr2_1MCg) 보호하는 Microsoft Azure 백업(26분 비디오)
- [시스템 ID 손상 복구](/azure/security/fundamentals/recover-from-identity-compromise)
- [Azure Sentinel에서 고급 다단계 공격 탐지](/azure/sentinel/fusion#ransomware)
- [Azure Sentinel의 랜섬웨어 퓨전 탐지](https://techcommunity.microsoft.com/t5/azure-sentinel/what-s-new-fusion-detection-for-ransomware/ba-p/2621373)

Microsoft Cloud App Security:

-  [Cloud App Security에서 이상 탐지 정책 생성](/cloud-app-security/anomaly-detection-policy)

Microsoft 보안 팀 블로그 게시물:

- [랜섬웨어 방지 및 복구를 위한 3단계(2021년 9월)](https://www.microsoft.com/security/blog/2021/09/07/3-steps-to-prevent-and-recover-from-ransomware/)
- [사이버 보안 위험 파악을 통한 탄력성 강화: 제4부—현재 위협 탐색(2021년 5월)](https://www.microsoft.com/security/blog/2021/05/26/becoming-resilient-by-understanding-cybersecurity-risks-part-4-navigating-current-threats/)

  **랜섬웨어** 섹션을 참조하세요.

- [인간 운영 랜섬웨어 공격: 예방 가능한 재해(2020년 3월)](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

  실제 공격에 대한 공격 체인 분석을 포함합니다.

- [랜섬웨어 대응—지불 여부(2019년 12월)](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)
- [Norsk Hydro가 랜섬웨어 공격에 투명하게 대응(2019년 12월)](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)
