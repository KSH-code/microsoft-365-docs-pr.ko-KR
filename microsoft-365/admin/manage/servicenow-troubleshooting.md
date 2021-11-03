---
title: ServiceNow와의 Microsoft 365 지원 문제 해결
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: ServiceNow에 대한 범위가 지정한 인증된 응용 프로그램 설치 및 구성 가이드입니다.
ms.openlocfilehash: 24813fe0d0705d9404fa465420e3b0344f43f953
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60661916"
---
# <a name="troubleshooting-microsoft-365-support-integration-with-servicenow"></a>ServiceNow와의 Microsoft 365 지원 문제 해결

| \#  | 문제  | 진단 작업     |
|-----|--------------------------------|----------------------|
| 1   | 지원 탭에서 **Microsoft 365 수** 없습니다.                                                                                                                                                                                    | 필터  &gt;  x \_ mioms \_ m365 \_ assit를 사용하여 현재 보기 및 시스템 로그 모두 확인                        |
| 2   | **Microsoft 권장 해결 방법을 선택하지만** "ServiceNow 관리자에게 문의하여 앱의 설정 단계를 완료해달라"는 오류가 발생합니다.                                                                      | 양식 맨 위에 오류 메시지 확인 **및** 시스템 로그 모두 필터 x &gt;  \_ mioms \_ m365 \_ assit     |
| 3    | **Microsoft 권장 해결 방법을 선택하지만** "ServiceNow 관리자에게 문의하여 앱에 대한 최종 설정 단계를 완료해달라"는 오류가 발생합니다.                                                                | 양식 맨 위에 오류 메시지 확인 **및** 시스템 로그 모두 필터 x &gt;  \_ mioms \_ m365 \_ assit     |
| 4   | 검색 상자에 문제를 입력하고 Microsoft 권장 해결 방법을 **선택하지만** "ServiceNow 관리자에게 문의하여 앱의 설정 단계를 완료해달라"는 오류가 발생합니다.                                   | 양식 맨 위에 오류 메시지 확인 **및** 시스템 로그 모두 필터 x &gt;  \_ mioms \_ m365 \_ assit     |
| 5   | 검색 상자에 문제를 입력하고 **Microsoft** 권장 해결 방법을 선택하지만 "ServiceNow 관리자에게 문의하여 앱에 대한 최종 설정 단계를 완료해달라"는 오류가 발생합니다.                                 | 양식 맨 위에 오류 메시지 확인 **및** 시스템 로그 모두 필터 x &gt;  \_ mioms \_ m365 \_ assit     |
| 6    | Microsoft **고객 지원에 문의를** 선택하고 "ServiceNow 관리자에게 문의하여 앱의 설정 단계를 완료해달라"는 오류가 표시됩니다.                                                                       | 양식 맨 위에 오류 메시지 확인 **및** 시스템 로그 모두 필터 x &gt;  \_ mioms \_ m365 \_ assit     |
| 7    | Microsoft 지원 서비스에 **문의를** 선택하고 "ServiceNow 관리자에게 문의하여 앱에 대한 최종 설정 단계를 완료해달라"는 오류가 발생합니다.                                                                 | 양식 맨 위에 오류 메시지 확인 **및** 시스템 로그 모두 필터 x &gt;  \_ mioms \_ m365 \_ assit     |
| 8    | Microsoft **지원에 문의하지만** "{EmailAddress}가 유효한 관리자 계정이 Microsoft 365 않습니다. 서비스 Microsoft 365 열기 위해 관리자 권한이 필요합니다. 앱에서 관리자 계정을 연결합니다." | 양식 맨 위에 오류 메시지 확인 **및** 시스템 로그 모두 필터 x &gt;  \_ mioms \_ m365 \_ assit     |
| 9    | **Microsoft 권장 솔루션을 선택하지만** 아무 것도 표시하지 않음                                                                                                                                                            | 시스템 **로그 확인 – 필터** 로그 및 필터가 있는 아웃바운드 HTTP login.microsoftonline.com connector.rave.microsoft.com |
| 10   | Microsoft **권장 솔루션을 선택하지만** "앱 지원에 문의하세요."라는 오류가 발생합니다.                                                                                                                                     | 양식 맨 위에 오류 메시지 확인 **및** 시스템 로그 모두 필터 x &gt;  \_ mioms \_ m365 \_ assit     |
| 11   | 검색 상자에 문제를 입력하고 **Microsoft** 권장 해결 방법 선택하지만 아무 것도 표시하지 않음                                                                                                                             | 시스템 **로그 확인 – 필터** 로그 및 필터가 있는 아웃바운드 HTTP login.microsoftonline.com connector.rave.microsoft.com |
| 12   | 검색 상자에 문제를 입력하고 Microsoft 권장 솔루션을 **선택하지만** "앱 지원에 문의하세요."라는 오류가 표시됩니다.                                                                                                      | 양식 맨 위에 오류 메시지 확인 **및** 시스템 로그 모두 필터 x &gt;  \_ mioms \_ m365 \_ assit     |
| 13  | 사용자가 **Microsoft 지원에 문의를 선택했지만** 아무 것도 일어나지 않습니다.                                                                                                                                                            | 시스템 **로그 확인 – 필터** 로그 및 필터가 있는 아웃바운드 HTTP login.microsoftonline.com connector.rave.microsoft.com |
| 14   | 인시던트 다시 열고 Microsoft 권장 솔루션을 볼 수 없습니다.                                                                                                                                                      | Check **System Logs** &gt; **All** with filter x \_ mioms \_ m365 \_ assit                                              |
| 15   | Microsoft 지원으로 전송된 인시던트 다시 열 때 Microsoft 사례를 볼 수 없습니다.                                                                                                                            | Check **System Logs** &gt; **All** with filter x \_ mioms \_ m365 \_ assit                                              |
| 16   | 티켓 세부 정보를 저장할 수 없습니다. "티켓 세부 정보를 저장할 수 없습니다. 앱 지원에 문의하세요."                                                                                                                          | 양식 맨 위에 있는 오류 메시지 확인                                                                            |
