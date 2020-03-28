---
title: 랜섬웨어 공격으로부터 복구
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Office 365 관리자는 랜 섬 웨어 공격 으로부터 복구 하는 방법에 대해 알아볼 수 있습니다.
ms.openlocfilehash: 6d57142bac6dad22d38cc26a9353b528a9f8eb10
ms.sourcegitcommit: d00efe6010185559e742304b55fa2d07127268fa
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/28/2020
ms.locfileid: "43032879"
---
# <a name="recover-from-a-ransomware-attack-in-office-365"></a>Office 365에서 랜 섬 웨어 공격 으로부터 복구

Office 365 조 직을 보호 하기 위해 모든 예방책을 사용 하는 경우에도 여전히 [랜 섬 웨어](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) 공격을 막을 수 있습니다. 랜 섬 웨어는 대규모 기업 이며, 공격은 정교 하 게 확인 됩니다.

이 항목의 단계에서는 랜 섬 웨어로 암호화 된 데이터를 복구할 수 있는 최상의 기회를 제공 하며, Office 365 조직에서 감염의 확산을 중지 하는 데 도움이 됩니다. 시작하기 전에 다음 항목을 고려하세요.

- Ransom의 비용을 지불 하면 파일에 대 한 액세스 권한이 반환 된다는 보장이 없습니다. 실제로 ransom를 지불할 경우 더 많은 랜 섬 웨어를 대상으로 할 수 있습니다. 이미 지불 되었지만 공격자의 확인을 사용 하지 않고 파일을 성공적으로 복구할 수 있는 경우에는 뱅크를 호출 하 여 트랜잭션을 차단할 수 있는지 확인 해야 합니다. 또한이 항목의 뒷부분에 설명 된 대로, 섬 웨어 공격을 법 집행, 사기 보고 웹 사이트 및 Microsoft에 보고 하는 것이 좋습니다.

- 공격에 빠르게 응답 하 고 그 결과를 처리 하는 것이 매우 중요 합니다. 기다리는 시간이 길수록 영향을 받는 데이터를 복구할 수 있다는 것을 덜 가능성이 줄어듭니다.

## <a name="step-1-verify-your-backups"></a>1 단계: 백업 확인

오프 라인 백업이 있는 경우 환경에서 맬웨어 (랜 섬 웨어 페이로드)를 제거한 **후** 에 암호화 된 데이터를 복원할 수 있습니다.

백업이 없거나 해당 백업이 랜 섬 웨어의 영향을 받는 경우에는이 단계를 건너뛰어도 됩니다.

## <a name="step-2-disable-activesync-and-onedrive-sync"></a>2 단계: ActiveSync 및 OneDrive 동기화를 사용 하지 않도록 설정

여기서 중요 한 점은 랜 섬 웨어에의 한 데이터 암호화 확산을 중지 하는 것입니다.

전자 메일이 대상이 되는 것으로 의심 되는 경우 사서함에 대 한 사용자 액세스를 일시적으로 사용 하지 않도록 설정 해야 합니다. Exchange ActiveSync는 모바일 장치에서 장치와 Exchange Online 사서함 간에 데이터를 동기화 하는 데 사용 됩니다.

사서함에 대해 ActiveSync를 사용 하지 않도록 설정 하려면 [Office 365에서 사용자에 대해 Exchange ActiveSync를 사용 하지 않도록 설정 하는 방법을](https://support.microsoft.com/help/2795303/how-to-disable-exchange-activesync-for-users-in-office-365)참조 하세요.

사서함에 대 한 다른 유형의 액세스를 사용 하지 않도록 설정 하려면 다음을 참조 하세요.

- [사서함에 대해 MAPI를 사용 하거나 사용 하지 않도록](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)설정 합니다.

- [사용자에 대해 POP3 또는 IMAP4 액세스를 사용 하거나 사용 하지 않도록 설정](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

OneDrive 동기화를 일시 중지 하면 잠재적으로 감염 된 장치에 의해 클라우드 데이터가 업데이트 되는 것을 방지할 수 있습니다. 자세한 내용은 [OneDrive에서 동기화 일시 중지 및 다시 시작 하는 방법을](https://support.office.com/article/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)참조 하세요.

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>3 단계: 영향을 받는 장치에서 맬웨어 제거

의심 되는 모든 컴퓨터 및 장치에 대 한 최신 업데이트를 사용 하 여 전체 바이러스 검사를 실행 하 여 랜 섬 웨어에 연결 된 페이로드를 검색 하 고 제거 합니다. 데이터를 동기화 하는 장치 또는 매핑된 네트워크 드라이브의 대상 (즉, 검색 해야 하는 컴퓨터와 장치)을 잊지 마십시오.

[Windows Defender](https://www.microsoft.com/windows/comprehensive-security) 또는 (이전 클라이언트용) [Microsoft Security Essentials](https://www.microsoft.com/download/details.aspx?id=5201)를 사용할 수 있습니다.

랜 섬 웨어 또는 맬웨어를 제거 하는 데 도움이 되는 또 다른 방법은 [악성 소프트웨어 제거 도구 (MSRT)](https://www.microsoft.com/download/details.aspx?id=9905)입니다.

이러한 옵션이 작동 하지 않으면 [Windows Defender offline](https://support.microsoft.com/help/17466/windows-defender-offline-help-protect-my-pc) 을 시도 하거나 [맬웨어 검색 및 제거 문제를 해결할](https://support.microsoft.com/help/4466982/windows-10-troubleshoot-problems-with-detecting-and-removing-malware)수 있습니다.

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>4 단계: 치료 된 컴퓨터 또는 장치에서 파일 복구

이전 단계를 완료 하 여 환경에서 랜 섬 웨어 페이로드를 제거한 후 (섬 웨어 파일을 암호화 하거나 제거 하지 못하게 함) windows 10 및 Windows 8.1의 [파일 기록을](https://support.microsoft.com/help/17128/windows-8-file-history) 사용 하 여 로컬 파일 및 폴더 복구를 시도할 수 있습니다.

**참고:**

- 일부 랜 섬 웨어도 백업 버전을 암호화 하거나 삭제 하므로 파일 기록 또는 시스템 보호를 사용 하 여 파일을 복원할 수 없습니다. 이 경우 다음 섹션에 설명 된 대로 랜 섬 웨어 또는 OneDrive의 영향을 받지 않았던 외부 드라이브 또는 장치에서 백업을 사용 해야 합니다.

- 폴더가 OneDrive에 동기화 되 고 최신 버전의 Windows를 사용 하지 않는 경우 파일 히스토리를 사용 하 여 몇 가지 제한이 있을 수 있습니다.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>5 단계: 비즈니스용 OneDrive에서 파일 복구

비즈니스용 OneDrive의 파일 복원 기능을 사용 하면 지난 30 일 이내에 이전 시점으로 전체 OneDrive를 복원할 수 있습니다. 자세한 내용은 [OneDrive 복원을](https://support.office.com/article/fa231298-759d-41cf-bcd0-25ac53eb8a15)참조 하세요.

## <a name="step-6-recover-deleted-email"></a>6 단계: 삭제 된 전자 메일 복구

드물지만 랜 섬 웨어가 모든 전자 메일을 삭제 한 경우에는 삭제 된 항목을 복구할 수 있습니다. 자세한 내용은 다음을 참조하세요.

- [사용자의 사서함에서 삭제된 메시지 복구](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Windows용 Outlook에서 삭제된 항목 복구](https://support.office.com/article/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>7 단계: Exchange ActiveSync 및 OneDrive 동기화 다시 사용

컴퓨터 및 장치를 청소 하 고 데이터를 복구한 후에는 [2 단계](#step-2-disable-activesync-and-onedrive-sync)에서 이전에 사용 하지 않도록 설정한 ActiveSync 및 OneDrive 동기화를 다시 사용 하도록 설정할 수 있습니다.

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>8 단계 (선택 사항): 특정 파일 확장명에 대 한 OneDrive 동기화 차단

복구한 후에는 비즈니스용 OneDrive 클라이언트에서이 랜 섬에 영향을 받은 파일 형식을 동기화 하지 못할 수 있습니다. 자세한 내용은 [get-spotenantsyncclientrestriction](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction) 를 참조 하세요.

## <a name="report-the-attack"></a>공격 보고

### <a name="contact-law-enforcement"></a>담당자 법률 집행

지역 또는 연방 법 집행 기관에 문의 해야 합니다. 예를 들어 미국에 있는 경우 [FBI 로컬 필드인 office](https://www.fbi.gov/contact-us/field), [IC3](http://www.ic3.gov/complaint/default.aspx) 또는 [Secret Service](http://www.secretservice.gov/)에 연결할 수 있습니다.

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>해당 국가의 사기 보고 웹 사이트로 보고서 제출

사기 보고 웹 사이트는 사기를 방지 하 고 방지 하는 방법에 대 한 정보를 제공 합니다. 또한 사기가 피해자 인지 여부를 보고 하는 메커니즘도 제공 합니다.

- 오스트레일리아: [Scamwatch](http://www.scamwatch.gov.au/)

- 캐나다: [캐나다 사기 방지 센터](http://www.antifraudcentre-centreantifraude.ca/)

- 프랑스: [agence de la sécurité des systèmes d'information](http://www.ssi.gouv.fr/)

- 독일: [Bundesamt Für Sicherheit in Der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- 아일랜드: [Garda Síochána](http://www.garda.ie/)

- 뉴질랜드: 소비자에 게 [사기](http://www.consumeraffairs.govt.nz/scams)

- 영국: [작업 사기](http://www.actionfraud.police.uk/)

- 미국: [온라인 보호 설정](http://www.onguardonline.gov/)

해당 국가가 나열 되지 않으면 지역 또는 연방 법 집행 기관에 문의 하세요.

### <a name="submit-email-messages-to-microsoft"></a>Microsoft로 전자 메일 메시지 제출

몇 가지 방법 중 하나를 사용 하 여 랜 섬 웨어가 포함 된 피싱 메시지를 보고할 수 있습니다. 자세한 내용은 [메시지 및 파일을 Microsoft에 보고](report-junk-email-messages-to-microsoft.md)를 참조 하세요.

## <a name="see-also"></a>참고 항목

- [랜](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [랜 섬 웨어 응답-비용 청구 또는 결제 안 하나요?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk Hydro 투명도를 사용한 랜 섬 웨어 공격에 응답](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [랜 섬 웨어 검색 및 OneDrive에서 파일 복구](https://support.office.com/article/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Microsoft 보안 인텔리전스 보고서](https://www.microsoft.com/securityinsights/)

- [Office 파일에서 매크로를 사용 하거나 사용 하지 않도록 설정](https://support.office.com/article/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [EOP 및 Office 365 ATP 보안에 대 한 권장 설정](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [훌륭한 업그레이드: Windows 10의 차세대 보안은 2017에서 랜 섬 웨어에 대 한 복원성을 입증 합니다.](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [Ma 없음, Samas:이 랜 섬 웨어의 modus 기능 andi](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [Locky 맬웨어, 피하는 운이 좋습니다.](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT 7 월 2016 일: (으)](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [Cerberus의 세 가지 헤드](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [Da 다빈치 코드의 영향을 받은 Troldesh 랜 섬 웨어](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
