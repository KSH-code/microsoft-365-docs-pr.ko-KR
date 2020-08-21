---
title: 랜섬웨어 공격으로부터 복구
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Microsoft 365 관리자는 랜웨어 공격을 복구하는 방법을 학습할 수 있습니다.
ms.openlocfilehash: 2f8e5f5deb18cadfaea7acc1cffe73abbc43010b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827836"
---
# <a name="recover-from-a-ransomware-attack-in-microsoft-365"></a>Microsoft 365에서 랜드웨어 공격으로부터 복구

조직을 보호하는 데 모든 예방 조치를 취한 경우에도 비전히 금의 [미분류방 공격에 취할 수](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware) 있습니다. 랜마마웨어는 비즈니스이며, 공격은 정체된지 확인해야 합니다.

이 항목의 단계에서는 랜니어로 암호화된 데이터를 복구할 수 있는 최선의 기회를 제공하며 이는 조직의 감염 확배를 중지하는 데 도움이 됩니다. 시작하기 전에 다음 항목을 고려하세요.

- 무결성을 지급하는 경우 파일의 액세스로 돌아가라고 한다는 보상은 없습니다. 사실 상실에 대응하면 더 많은 임의 대상이 되는 임의의 대상이 됩니다. 이미 유료했지만 공격자의 해상도를 사용하지 않고도 파일을 성공적으로 복구할 수 있었다면 은행에 전화하여 거래를 차단할 수 있는지 확인해야 합니다. 또한 이 항목의 뒷부분에 설명된 법 적용, 사법 보고 웹 사이트 및 Microsoft에 내용 분석 공격을 보고하는 것이 좋습니다.

- 공격 및 그 영향에 신속하게 대응하는 것이 매우 중요합니다. 대기 시간이 길수가 길수는 영향을 받는 데이터를 복구할 수 있다는 것이 작습니다.

## <a name="step-1-verify-your-backups"></a>1단계: 백업 확인

오프라인 백업이 있는 경우 환경에서 Ransomware **after** 페이로드(맬웨어)를 제거한 후 암호화된 데이터를 복원할 수 있습니다.

백업이 없는 경우 또는 백업이 이 임계의 영향을 받도 한 경우 이 단계를 건너뛸 수 있습니다.

## <a name="step-2-disable-activesync-and-onedrive-sync"></a>2단계: ActiveSync 및 OneDrive 동기화를 사용하지 않도록 설정

여기에 서점은 이 요인에 의한 데이터 암호화 확정을 중지하는 것이며,

이 전자 메일이 대상으로 의심되는 경우 사서함의 사용자 액세스를 일시적으로 사용하지 않도록 설정해야 합니다. Exchange ActiveSync 장치에서 장치와 Exchange Online 사서함 간에 데이터를 동기화하는 데 사용됩니다.

사서함에 대해 ActiveSync를 사용하지 않도록 설정하려면 [Exchange Online에서 사용자를 위한 Exchange ActiveSync 방법을 참조하세요.](https://support.microsoft.com/help/2795303)

사서함에 대한 다른 유형의 액세스를 비활성화하려면 다음을 참조하세요.

- [사서함에 대해 MAPI를 사용하도록 또는 사용하지 않도록 설정합니다.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-mapi)

- [사용자에 대해 POP3 또는 IMAP4 액세스 사용 또는 사용 안 함](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/pop3-and-imap4/enable-or-disable-pop3-or-imap4-access)

OneDrive 동기화를 해제하면 잠재적으로 디바이스에 의해 클라우드 데이터가 업데이트되지 않도록 보호할 수 있습니다. 자세한 내용은 [OneDrive에서 동기화를 시작 및 다시 시작하는 방법을 참조하세요.](https://support.microsoft.com/office/2152bfa4-a2a5-4d3a-ace8-92912fb4421e)

## <a name="step-3-remove-the-malware-from-the-affected-devices"></a>3단계: 영향을 받는 장치에서 맬웨어 제거

의심되는 모든 컴퓨터 및 장치에서 최신 업데이트로 전체 바이러스 백신 검사를 실행하여 해당 루프로워웨어와 연결된 페이로드를 검색 및 제거합니다. 데이터를 동기화하는 디바이스 또는 매핑된 네트워크 드라이브의 대상을 대상으로 하는 디바이스를 다루지 마세요.

필요한 이름 [또는 Windows Defender(이전](https://www.microsoft.com/windows/comprehensive-security) 클라이언트의 경우)을 [사용할 Microsoft Security Essentials.](https://www.microsoft.com/download/details.aspx?id=5201)

또한 환경 및 맬웨어를 제거하는 데 도움이 될 수 있는 또 다른 방법은 [MSRT(악성 소프트웨어 제거 도구)입니다.](https://www.microsoft.com/download/details.aspx?id=9905)

이러한 옵션이 작동하지 않는 경우 [오프라인으로 Windows Defender 사용하여](https://support.microsoft.com/help/17466) [문제를 해결하고 맬웨어를 제거하는 데 문제를 해결할 수 있습니다.](https://support.microsoft.com/help/4466982)

## <a name="step-4-recover-files-on-a-cleaned-computer-or-device"></a>4단계: 제거된 컴퓨터 또는 장치에서 파일 복구

이전 단계를 완료하여 환경의 랜지웨어 페이로드를 제거한 후(랜니어로 파일을 암호화하거나 제거하는 일이 방지됨) Windows 10의 [File History](https://support.microsoft.com/help/17128) 파일 기록을 사용하거나 Windows 7의 Windows 8.1 또는 시스템 보호를 사용하여 로컬 파일 및 폴더를 복구할 수 있습니다.

**참고:**

- 일부 루마치는 백업 버전도 암호화하거나 삭제하므로 파일 기록 또는 시스템 보호를 사용하여 파일을 복원할 수 없습니다. 이 경우 다음 섹션에 설명된 것과 같이, 외부 드라이브 또는 리스마크웨어나 OneDrive의 영향을 받지 않은 장치에서 백업을 수행해야 합니다.

- 폴더가 OneDrive와 동기화되고 사용자가 최신 버전의 Windows를 사용하고 있는 경우 파일 기록을 사용하여 몇 가지 제한이 있을 수 있습니다.

## <a name="step-5-recover-your-files-in-your-onedrive-for-business"></a>5단계: 비즈니스용 OneDrive에서 파일 복구

비즈니스용 OneDrive에서 파일을 복원하면 전체 OneDrive를 지난 30일 이내의 이전 시점으로 복원할 수 있습니다. 자세한 내용은 [OneDrive 복원을 참조하세요.](https://support.microsoft.com/office/fa231298-759d-41cf-bcd0-25ac53eb8a15)

## <a name="step-6-recover-deleted-email"></a>6단계: 삭제된 전자 메일 복구

드의 경우에는 랜지 나의 경우 매시어나 모든 전자 메일을 삭제한다는 것이 확신이 있습니다. 자세한 내용은 다음을 참조하세요.

- [사용자의 사서함에서 삭제된 메시지 복구](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages)

- [Windows용 Outlook에서 삭제된 항목 복구](https://support.microsoft.com/office/49e81f3c-c8f4-4426-a0b9-c0fd751d48ce)

## <a name="step-7-re-enable-exchange-activesync-and-onedrive-sync"></a>7단계: 구성 및 OneDrive Exchange ActiveSync 사용

컴퓨터 및 장치를 지우고 데이터를 복구한 [후에는 이전에 2단계에서](#step-2-disable-activesync-and-onedrive-sync)사용하지 않도록 설정한 ActiveSync 및 OneDrive 동기화를 다시 사용하도록 설정할 수 있습니다.

## <a name="step-8-optional-block-onedrive-sync-for-specific-file-extensions"></a>8단계(옵션): 특정 파일 확장명에 대한 OneDrive 동기화 차단

복구후에는 비즈니스용 OneDrive 클라이언트가 이 랜더리를 통해 영향을 받는 파일 형식을 동기화하지 못하도록 방지할 수 있습니다. 자세한 내용은 [Set-SPOTenantSyncClientRestriction을 참조하세요.](https://docs.microsoft.com/powershell/module/sharepoint-online/set-spotenantsyncclientrestriction)

## <a name="report-the-attack"></a>공격 보고

### <a name="contact-law-enforcement"></a>연락처 법 기고

지역 또는 연사 법 기관에 문의해야 합니다. 예를 들어 미국에 있는 경우 [FBI](https://www.fbi.gov/contact-us/field)로컬 필드 사무실, [IC3 또는](http://www.ic3.gov/complaint/default.aspx) [Secret Service에 문의할 수 있습니다.](http://www.secretservice.gov/)

### <a name="submit-a-report-to-your-countrys-scam-reporting-website"></a>국가의 SCAM 보고 웹 사이트에 보고서 제출

Scam 보고 웹 사이트는 스캐밍을 방지하고 피하는 방법에 대한 정보를 제공합니다. 또한 사기가 고용되었는지 보고하는 메커니즘을 제공합니다.

- 오스트레일리아: [SCAMwatch](http://www.scamwatch.gov.au/)

- 캐나다: [캐나다 앤티 Anti-Fraud Centre](http://www.antifraudcentre-centreantifraude.ca/)

- 프랑스: [Agence nationale de la sécurité des systémes d'information](http://www.ssi.gouv.fr/)

- 독일: [Bundesamt fêr Sicherheit der Informationstechnik](https://www.bsi.bund.de/DE/Home/home_node.html)

- 아일랜드: [Garda Síochána](http://www.garda.ie/)

- 뉴질레드: [소비자 호수 사기](http://www.consumeraffairs.govt.nz/scams)

- 영국: [소방](http://www.actionfraud.police.uk/) 조치

- 미국: [온라인 보호](http://www.onguardonline.gov/)

해당 국가에 목록이 없는 경우 지역 또는 연사 법 기관에 질의하세요.

### <a name="submit-email-messages-to-microsoft"></a>Microsoft에 전자 메일 메시지 제출

여러 방법 중 하나를 사용하여 운동리문제가 있는 피싱 메시지를 보고할 수 있습니다. 자세한 내용은 [Microsoft에 메시지와 파일 보고](report-junk-email-messages-to-microsoft.md)를 참조하세요.

## <a name="see-also"></a>참고 항목

- [리체계웨어](https://docs.microsoft.com/windows/security/threat-protection/intelligence/ransomware-malware)

- [Ransomware 응답 — 지급되지 않나요?](https://www.microsoft.com/security/blog/2019/12/16/ransomware-response-to-pay-or-not-to-pay/)

- [Norsk Hydro는 투명성으로 운전 웨어웨어 공격에 대응합니다.](https://www.microsoft.com/security/blog/2019/12/17/norsk-hydro-ransomware-attack-transparency/)

- [랜스니아 감지 및 OneDrive에서 파일 복구](https://support.microsoft.com/office/0d90ec50-6bfd-40f4-acc7-b8c12c73637f)

- [Microsoft 보안 인텔리전스 보고서](https://www.microsoft.com/securityinsights/)

- [Office 파일에서 매크로 사용 또는 사용 안 함](https://support.microsoft.com/office/12b036fd-d140-4e74-b45e-16fed1a7e5c6)

- [EOP 및 Office 365 ATP 보안에 대한 권장 설정](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp)

- [업그레이드 이한 이점: Windows 10의 차세대 보안으로 2017년 에너지 고지에 대해 확실한 개식적 분석](https://www.microsoft.com/security/blog/2018/01/10/a-worthy-upgrade-next-gen-security-on-windows-10-proves-resilient-against-ransomware-outbreaks-in-2017/)

- [그 몰래, Samas: 이 금전지의 영국 동의어는 어떤 말인가요?](https://www.microsoft.com/security/blog/2016/03/17/no-mas-samas-whats-in-this-ransomwares-modus-operandi/)

- [맬웨어 잠금, 맬웨어가 방지되는 작업](https://www.microsoft.com/security/blog/2016/02/24/locky-malware-lucky-to-avoid-it/)

- [MSRT July 2016: Cerber ransomware](https://www.microsoft.com/security/blog/2016/07/12/msrt-july-2016-cerber-ransomware/)

- [사이버 같은 Cerberus와 같은 세 가지 위치의 위의 기향](https://www.microsoft.com/security/blog/2016/03/09/the-three-heads-of-the-cerberus-like-cerber-ransomware/)

- [아체베이스 코드에 의해 영향을 받은 Troldesh 루프웨어](https://www.microsoft.com/security/blog/2016/07/13/troldesh-ransomware-influenced-by-the-da-vinci-code/)
