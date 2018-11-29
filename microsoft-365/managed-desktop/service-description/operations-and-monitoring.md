---
title: Microsoft 관리 되는 데스크톱 운영 및 모니터링
description: ''
keywords: Microsoft 관리 되는 데스크톱, Microsoft 365 서비스, 설명서
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 00bdc95c191ce16be219cf0dc251f72eaf054e22
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869893"
---
# <a name="microsoft-managed-desktop-operations-and-monitoring"></a>Microsoft 관리 되는 데스크톱 운영 및 모니터링

<!-- Operations and monitoring: -->


## <a name="change-management"></a>변경 관리

Microsoft와 고객 데스크톱을 관리 하는 Microsoft 서비스에 대 한 변경 관리를 공유 합니다. 온-프레미스 서버 또는 클라이언트와 온라인 서비스에 대 한 책임을 부여 달라 집니다. 

### <a name="change-process-overview"></a>변경 프로세스 개요 (영문)

다음은 변경 하는 프로세스는 Microsoft와 고객 간에 공유 하는 방법의 요약 합니다. 



<table>
<tr><th></th><th><p>Microsoft을 수행합니다.</p></th><th><p>고객을 수행합니다.</p></th></tr>
<tr><td>변경 전</td><td><ul><li>관리자가 작업을 필요로 하는 변경 내용에 대 한 미리 5 일을 고객에 게 알려야 합니다.</li><li>긴급 변경 내용을 알리는 하기 전에 완화를 적용 합니다.</li></ul></td><td><ul><li>읽기 및 알림 전자 메일을 이해 합니다.</li><li>인정 하 고이 필요한 경우 승인 합니다.</li></ul></td></tr><tr><td>변경 도중</td><td><ul><li>Windows 10과 Office에 대 한 변경 내용을 배포, 필요에 따라 보안 및 비보안 업데이트를 해제 합니다.</li><li>예기치 않은 문제에 대한 원격 분석을 모니터링하고 에스컬레이션을 지원합니다.</li></ul></td><td><ul><li>내부 변경 관리 프로세스를 관리 합니다.</li><li>필요한 경우 지원 요청을 만듭니다.</li></ul></td></tr><tr><td>변경 후</td><td><ul><li>향후 변경의 배포를 향상 시키기 위해 고객 의견을 수집 합니다.</li><li>예기치 않은 문제에 대한 원격 분석을 모니터링하고 에스컬레이션을 지원합니다.</li></ul></td><td><ul><li>읽기 및 알림 전자 메일을 이해 합니다.</li><li>일반 사용자 의견 및 관리 피드백 도구에서 특정 사용자 의견을 제공 합니다.</li><li>Office 응용 프로그램에서 Windows 피드백 허브 및 Smile 단추를 사용 하 여 응용 프로그램 관련 의견을 제공 하는 사용자를 교육 합니다.</li></ul></td></tr>
<table> 






### <a name="change-types"></a>형식을 변경 합니다.

여러 유형의 주기적으로 서비스에 적용 된 변경 내용이 있습니다. 이러한 변경 사항 및 고객에 게는 담당 하는 작업에 대 한 통신 채널 달라 집니다.

다음과 같은 유형의 변경 내용을 예상할 수 있습니다.

유형 변경 | 알림 | 고객 작업
--- | --- | ---
업데이트 및 서비스 구성 요소를 새로운 기능 | 전자 메일 | --사용자에 게 변경 통신 하는 중<br><br> -Microsoft에서 필요에 따라 act<br><br> 48 시간 내를 선택한 다음 작업을 수행 해야 합니다.
보안 업데이트를 매월 업데이트 및 초기 계획 설정 모두 | 전자 메일, 보안 공지 또는 공통 취약점 및 노출 (c v E) 항목 | -월별 보안 사용해 [업데이트 관리 전략을](updates.md)사용 하 여 업데이트를 배포 됩니다.<br><br> -설정 위협을 완화 하 여 조직을 보호 하기 위해 전체 조직에 배포 됩니다. (이 표시 되지 않음 고객 작업 수)
서비스 업데이트 핫픽스와 비보안 영향을 받는 기본 정책 등 품질 업데이트 | 전자 메일 | 필요한 경우에 게 됩니다.
긴급 업데이트: 완화 하기 위해 서비스, 구성 또는 소프트웨어 업데이트 requred:<br><br> 중요 한 보안 위험<br><br> -잠재적 데이터 손실<br><br> -원격 분석 데이터에 대 한 액세스 Microsoft 관리 되는 데스크톱 장치 관리 | 필요한 경우에 게 됩니다.

## <a name="standard-operating-procedures"></a>표준 운영 절차

이 서비스를 구현 하 여 다른 관리 작업을 수행 하면 환경에서 microsoft 운영 합니다. Microsoft는 Microsoft 관리 되는 데스크톱 관련 설치, 구성 및 작업에 대 한 모든 책임을 집니다. 

온-프레미스 제품에 대 한 조직 운영 관리 및 구성 작업에 대 한 모든 책임에 적용 됩니다.

Categories |    동작
--- | ---
서비스 계정 |  Microsoft을 수행합니다.<br><br> -구현, 안전 하 게 저장 하 고 자격 증명 관리<br><br> -통신 무단으로 액세스 하거나 보안 작업 팀에 이러한 자격 증명 사용<br><br><br><br>고객을 수행합니다.<br><br> -엽니다 정보 지원 요청 데스크톱 작업을 관리 하는 Microsoft 계정에 영향을 줄 수 있는 변경을 계획 하는 경우<br><br> -정책, 다단계 인증, 조건부 액세스 또는 응용 프로그램 배포 Microsoft 관리 되는 데스크톱 서비스 계정에 할당 하지<br><br> --암호 다시 설정 하거나 자격 증명을 사용 하 여<br><br> -이러한 서비스 계정에 관련 된 Intune 또는 Azure 감사 로그에서 의심 스러운 활동 관찰 되는 경우 Microsoft 관리 되는 데스크톱 작업을 Sev C 지원 요청을 열
장치 그룹 | Microsoft을 수행합니다.<br><br> -구현 하 고 데스크톱을 관리 하는 Microsoft 그룹 내에서 장치의 구성원 관리<br><br> -배정 및 장치를 구성 및 업데이트의 버전을 관리 하는 데스크톱을 관리 하는 Microsoft 그룹을 사용 합니다.<br><br><br><br>고객을 수행합니다.<br><br> -열 정보 지원 요청 데스크톱 작업을 관리 하는 Microsoft와 그룹에 영향을 줄 수 있는 변경을 계획 하는 경우<br><br> -모든 데스크톱을 관리 하는 Microsoft 그룹의 구성원 자격을 수정 하지<br><br> -만 그룹을 사용 하 여 비즈니스 또는 전자 메일 암호화 또는 회사 Wi-fi 프로필 구성에 대 한 VPN, Windows Hello 등의 서비스에 대 한 회사 인증서를 할당 하려면<br><br> -공동 관리 존재 하는 위치, 구성 관리자 클라이언트를 배포할 때 모든 데스크톱을 관리 하는 Microsoft 그룹을 명시적으로 제외
Policies(정책) |  Microsoft을 수행합니다.<br><br> -구현 하 고 서비스 내에서 장치 구성 상태를 제어 하는 Microsoft 관리 되는 데스크톱 정책 관리<br><br> -정책 또는 증분 장치 그룹을 사용 하 여 Windows 업데이트를 배포 합니다.<br><br> -명시적으로 대상 비-Microsoft 관리 되는 데스크톱 그룹을 제외<br><br><br><br>고객을 수행합니다.<br><br> -열에서 정보 지원 티켓 데스크톱 작업을 관리 하는 Microsoft와 장치의 원하는 구성 상태에 영향을 줄 수 있는 변경을 계획 하는 경우<br><br> --편집 하거나 장치 또는 데스크톱을 관리 하는 Microsoft 서비스에서 관리 하지 않는 사용자에 게 Microsoft 관리 되는 데스크톱 정책 할당
Windows Defender Advanced Threat Protection | Microsoft을 수행합니다.<br><br> -모니터링 및 관리 하는 데스크톱 Microsoft 서비스의 범위 내에서 장치를 조사 합니다.<br><br><br><br>고객을 수행합니다.<br><br> -열에서 정보 지원 티켓 데스크톱 작업을 관리 하는 Microsoft와 Microsoft 관리 되는 데스크톱 보안 작업 센터의 모니터링 또는 조사 기능에 영향을 줄 수 있는 변경을 계획 하는 경우
비즈니스용 Microsoft Store |  Microsoft을 수행합니다.<br><br> -구성 및 관리 하는 데스크톱 Microsoft 서비스에 대 한 Windows 작업을 자동화할 프로필을 유지 관리<br><br><br><br>고객을 수행합니다.<br><br> -열에서 정보 지원 티켓 데스크톱 작업을 관리 하는 Microsoft와 열기 저장소에 대 한 액세스에 영향을 줄 수 또는 Microsoft 관리 되는 데스크톱 Windows 작업을 자동화할 프로필을 수정 하는 변경을 계획 하는 경우<br><br> -Microsoft 관리 되는 데스크톱 Windows 작업을 자동화할 프로필의 구성을 수정 하지 또는 할당 된 장치를 추가/제거 합니다.
인증서 |  고객을 수행합니다.<br><br> -모든 인증서가 만료 되기 전에 Microsoft 관리 되는 데스크톱 작업 60 일와 정보 지원 티켓을 열고 합니다.<br><br> --구성 하는 데 필요한 모든 인증서를 업데이트 하는 중: 프로필, VPN 프로필 및 Wi-fi 프로필 인증서



## <a name="device-wipe-with-factory-reset"></a>공장 초기화 된 장치 지우기

관리 되는 데스크톱 운영팀 공장을 수행할 수 있는 이미지를 다시 만들 수 있는 Microsoft 관리 되는 데스크톱에서 관리 하는 장치에서 다시 설정 합니다. 장치 귀하는 다른 직원에 게 해야하는 경우 또는 직원이 회사를 떠날 하는 경우에 유용 합니다. 

몇가지 요구 사항이 있습니다.

- 고객의 테 넌 트 관리자가 보내는 서비스 요청을 전송 해야
- 필요한 장치에 대 한 컴퓨터 이름
- 사용자 계정을 다시 설정 하는 작업을 수행 하기 전에 Azure AD에 있어야 합니다.

관리 되는 데스크톱 작업 팀을 수행합니다.

- Intune에서 장치 이름 조회
- 공장 장치에 명령을 다시 보내기

>[!NOTE]
>공장 초기화 하기 전에 Azure AD에서 사용자 계정을 제거 하지 마십시오. 사용자 Azure AD에 없으면 Intune 공장 장치 기본값으로 다시 설정 명령을 보낼 수 없습니다. 

장치 OOBE로 부팅 하 고 모든 사전 설치 된 응용 프로그램 및 설정을 다시 적용 됩니다. 장치의 사용자가 초기 설정 정보를 다시 제공 해야 합니다. 

장치를 다시 설정 하는 경우 조직에 다른 사람에 게 제공할 수 있습니다. 이전 사용자의 데이터 또는 엔터프라이즈 데이터 없음 장치에 됩니다. 다음 사용자를 이전 사용자는 새 Microsoft 관리 되는 데스크톱 장치와 동일한 프로세스를 통해 들어갈 수 있습니다.

BitLocker는이 프로세스에서 데이터 보안의 주요 구성 요소입니다. 공장 초기화 장치에 적용 된 후에 Microsoft 관리 되는 데스크톱 장치에서 BitLocker 암호화로 드라이브에 데이터의 보안 유지 합니다. 드라이브에 있던 모든 데이터 장치의 다음 사용자에 게 제공 되지 않습니다. 자세한 내용은 [BitLocker 개요](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)를 참조 하십시오.

자세한 내용은 [공장 장치 재설정](https://docs.microsoft.com/intune/devices-wipe#factory-reset-a-device)을 참조 하십시오. 
