---
title: Office 앱에서 민감도 레이블 작동 방식
ms.author: greglin
author: greg-lindsay
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 민감도 레이블을 사용하여 사용자의 생산성 및 공동 작업 능력이 저하되지 않도록 하면서 중요한 콘텐츠를 분류 및 보호할 수 있습니다. 민감도 레이블을 사용하여 레이블이 지정된 콘텐츠에 대해 암호화 또는 워터마크와 같은 보호 설정을 적용할 수 있습니다.
ms.openlocfilehash: f702423f0b1074b5619ef1c321cc5e9f1daef1d7
ms.sourcegitcommit: 15173ab87325b7d79bab683702b35d77a355cd6b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/08/2019
ms.locfileid: "37417567"
---
# <a name="how-sensitivity-labels-work-in-office-apps"></a>Office 앱에서 민감도 레이블 작동 방식

## <a name="what-prerequisites-are-there-to-use-sensitivity-labels-in-office-applications"></a>Office 응용 프로그램에서 민감도 레이블을 사용하는 데 필요한 필수 사항은 무엇인가요?

### <a name="common-requirements"></a>일반적인 요구 사항 

- 통합 민감도 레이블은 [보안 및 준수 센터에서 구성되고 게시](https://aka.ms/managemip)되어야 합니다.
- 사용자는 회사 계정으로 Office에 로그인해야 합니다.
- 사용자에게는 Office 365 E3 이상의 라이선스가 할당되어 있어야 합니다.

### <a name="additional-requirements-for-office-for-windows"></a>Windows용 Office에 대한 추가 요구 사항 

- Azure Information Protection 클라이언트가 Office에서 실행되고 있지 않아야 합니다. 참고 항목: [Windows용 Office에서 민감도 레이블을 Azure Information Protection 클라이언트와 함께 실행할 수 있나요?](#can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows)

### <a name="additional-requirements-for-outlook-on-all-platforms"></a>모든 플랫폼에서 Outlook에 대한 추가 요구 사항 

- 레이블 구성에서 콘텐츠 표시를 설정하는 경우에는 Exchange Online을 사용하여 전송에 콘텐츠 표시를 삽입해야 합니다.

## <a name="what-sensitivity-label-capabilities-are-supported-in-office-today"></a>현재 Office에서는 어떤 민감도 레이블 기능이 지원되나요? 

<table border="1" cellspacing="0" cellpadding="0">
<th><font size="-1">기능<th><font size="-1">Windows<th><font size="-1">Mac<th colspan="2"><font size="-1">iOS<th colspan="2"><font size="-1">Android<th colspan="2"><font size="-1">Web</tr>
<tr><td>

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint<br>
Outlook


<td><font size="-1"> Word<br>
Excel<br>
PowerPoint<br>
Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook

<td><font size="-1"> Word<br>
Excel<br>
PowerPoint
<td><font size="-1"> Outlook </b>
</tr>

<tr>
<td><font size="-1">수동으로 레이블 적용, 변경 또는 제거<td><font size="-1"><b>예</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>예</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>예</b><br><font size="-1">2.21+</font>
<td><font size="-1">출시 예정<sup>3</sup>
<td><font size="-1"><b>예</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">출시 예정<sup>3</sup>
<td><font size="-1">출시 예정<sup>3</sup><td><font size="-1">출시 예정<sup>3</sup>

<tr>
<td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">기본 레이블 적용</a>
<td><font size="-1"><b>예</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>예</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>예</b><br><font size="-1">2.21+</font>
<td><font size="-1">출시 예정<sup>3</sup>
<td><font size="-1"><b>예</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">출시 예정<sup>3</sup>
<td><font size="-1">출시 예정<sup>3</sup>
<td><font size="-1">출시 예정<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">레이블을 변경하는 데 사유 요구</a><sup>1</sup>
<td><font size="-1"><b>예</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>예</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>예</b><br><font size="-1">2.21+</font>
<td><font size="-1">출시 예정<sup>3</sup>
<td><font size="-1"><b>예</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">출시 예정<sup>3</sup>
<td><font size="-1">출시 예정<sup>3</sup>
<td><font size="-1">출시 예정<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">사용자 지정 도움말 페이지에 도움말 링크 제공</a>
<td><font size="-1"><b>예</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>예</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>예</b><br><font size="-1">2.21+</font>
<td><font size="-1">출시 예정<sup>3</sup>
<td><font size="-1"><b>예</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">출시 예정<sup>3</sup>
<td><font size="-1">출시 예정<sup>3</sup>
<td><font size="-1">출시 예정<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels#what-sensitivity-labels-can-do">콘텐츠 표시</a>
<td><font size="-1"><b>예</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>예</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>예</b><br><font size="-1">2.21+</font>
<td><font size="-1">출시 예정<sup>3</sup>
<td><font size="-1"><b>예</b><br><font size="-1">16.0.11231+</font
><td><font size="-1">출시 예정<sup>3</sup>
<td><font size="-1">출시 예정<sup>3</sup>
<td><font size="-1">출시 예정<sup>3</sup>

<tr><td><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/encryption-sensitivity-labels#assign-permissions-now">사전 정의된 사용 권한 할당</a>
<td><font size="-1"><b>예</b><br><font size="-1">1910+</font>

<td><font size="-1"><b>예</b><br><font size="-1">16.21.0+</font>

<td><font size="-1"><b>예</b><br><font size="-1">2.21+</font>
<td><font size="-1">출시 예정<sup>3</sup>
<td><font size="-1"><b>예</b><br><font size="-1">16.0.11231+</font>
<td><font size="-1">출시 예정<sup>3</sup>
<td><font size="-1">출시 예정<sup>3</sup>
<td><font size="-1">출시 예정<sup>3</sup>

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels#let-users-assign-permissions">사용자가 권한을 할당하도록 허용</a>
<td><font size="-1"><b>예</b><sup>2</sup><br><font size="-1">1910+</font>

<td><font size="-1"><b>예</b><sup>2</sup><br><font size="-1">16.21.0+</font>

<td><font size="-1">TBD
<td><font size="-1">출시 예정<sup>3</sup>
<td><font size="-1">TBD<td
><font size="-1">출시 예정<sup>3</sup>
<td><font size="-1">TBD
<td><font size="-1">출시 예정<sup>3</sup>

<tr><td><font size="-1">관리자를 위한 <a href="https://docs.microsoft.com/microsoft-365/compliance/label-analytics">레이블 분석</a> 데이터 보내기
<td><font size="-1">TBD

<td><font size="-1">TBD

<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD

<tr><td><font size="-1">
  <a href="https://docs.microsoft.com/en-us/microsoft-365/compliance/sensitivity-labels#what-label-policies-can-do">사용자가 전자 메일 및 문서에 레이블을 적용하도록 요구</a>
<td><font size="-1">TBD

<td><font size="-1">TBD

<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD

<tr><td><font size="-1"><a href="https://docs.microsoft.com/microsoft-365/compliance/apply-sensitivity-label-automatically">민감도 레이블을 콘텐츠에 자동으로 적용</a>
<td><font size="-1">TBD

<td><font size="-1">TBD

<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
<td><font size="-1">TBD
</table>

<br><sup>1</sup>구성된 경우 사용자에게 레이블 다운그레이드를 정당화하라는 메시지가 표시됩니다. 그러나 아직 관리자는 사유 데이터를 사용할 수 없습니다. "관리자를 위한 레이블 분석 데이터 보내기" 기능이 지원 되는 경우 이 기능을 사용할 수 있게 됩니다.
<br><sup>2</sup>사용자가 권한을 할당하도록 허용은 현재 Windows 및 Mac용 Outlook에서만 사용할 수 있습니다. Word, Excel 및 PowerPoint의 사용 가능성은 TBD입니다.
<br><sup>3</sup>2019년 4분기 예상

## <a name="when-do-content-marks-or-encryption-get-applied-after-content-is-given-a-sensitivity-label"></a>콘텐츠에 민감도 레이블이 지정된 후 콘텐츠 표시 또는 암호화가 적용되는 시점은 언제인가요?

| 응용 프로그램 | 콘텐츠 표시 | 암호화
| --- | --- | --- |
| 모든 플랫폼의 Word, Excel, PowerPoint | 즉시 | 즉시 |
| PC 및 Mac용 Outlook | Exchange Online에서 전자 메일을 보낸 후 | 즉시 |
| Mac, iOS 및 Android용 Outlook | Exchange Online에서 전자 메일을 보낸 후 | Exchange Online에서 전자 메일을 보낸 후 |

## <a name="can-sensitivity-labels-run-alongside-the-azure-information-protection-client-in-office-for-windows"></a>Windows용 Office에서 민감도 레이블을 Azure Information Protection 클라이언트와 함께 실행할 수 있나요?

아니요. Windows용 Office에서 Azure Information Protection 클라이언트를 로드하면 민감도 레이블이 꺼집니다.

Azure Information Protection 클라이언트가 설치되어있지만 대신 민감도 레이블을 사용하려면 다음을 수행할 수 있습니다.

1.  **Office에서 민감도 기능을 사용하여 민감도 레이블을 적용하고 보도록** 그룹 정책 설정을 구성합니다. 이 설정은 **사용자 구성/관리 템플릿/Microsoft Office 2016/보안 설정**에 있습니다. 

  >참고: 이 설정은 기존 그룹 정책 배포 메커니즘 또는 [Office 클라우드 정책 서비스](https://docs.microsoft.com/DeployOffice/overview-office-cloud-policy-service)를 통해 배포될 수 있습니다. 
 
  또는 Azure Information Protection 클라이언트를 제거하거나  [사용지 않도록](https://support.office.com/article/view-manage-and-install-add-ins-in-office-programs-16278816-1948-4028-91e5-76dca5380f8d) 설정할 수 있습니다. 

2. 모든 Office 응용 프로그램을 다시 시작합니다.

## <a name="will-sensitivity-labels-be-supported-in-non-subscription-versions-of-office-like-office-2016-or-office-2019"></a>Office 2016 또는 Office 2019와 같은 비구독 버전의 Office에서 민감도 레이블이 지원되나요?

아니요. 민감도 레이블은 Office 365 구독에서만 지원되고 비구독 버전에서는 지원되지 않습니다. 그러나 Azure Information Protection 통합 레이블 클라이언트는 비등록 버전의 Office에서 사용할 수 있습니다. 

## <a name="i-previously-deployed-protection-templates-before-setting-up-sensitivity-labels-where-did-they-go"></a>민감도 레이블을 설정하기 전에 이전에 보호 템플릿을 배포했습니다. 어디에 있나요?

관리자 정의 [보호 템플릿](https://docs.microsoft.com/azure/information-protection/configure-policy-templates)은 민감도 레이블이 사용되는 경우 암호화가 설정된 민감도 레이블과 중복되므로 Office 사용자 환경에서 숨겨집니다. 

## <a name="can-a-file-or-email-have-more-than-one-classification"></a>파일 또는 전자 메일에 분류가 여러 개 있을 수 있나요?

아니요. 사용자는 각 문서 또는 전자 메일에 대해 한 번에 하나의 레이블만 선택할 수 있습니다.

## <a name="when-an-email-is-labeled-do-any-attachments-automatically-get-the-same-labeling"></a>전자 메일에 레이블을 지정하면 모든 첨부 파일에 자동으로 같은 레이블이 지정되나요?

아니요. 첨부 파일이 포함된 전자 메일 메시지에 레이블을 지정하는 경우 해당 첨부 파일은 같은 레이블을 상속하지 않습니다. 첨부 파일은 레이블이 없는 상태로 유지되거나 따로 적용된 레이블이 유지됩니다. 그러나 전자 메일에 대한 레이블이 보호를 적용하는 경우 해당 보호는 Office 첨부 파일에 적용됩니다.

## <a name="additional-resources"></a>추가 리소스

[Azure Information Protection의 분류 및 레이블링에 대한 질문과 대답](https://docs.microsoft.com/azure/information-protection/faqs-infoprotect)<br>
[Office 내의 문서 및 전자 메일에 민감도 레이블 적용](https://support.office.com/article/apply-sensitivity-labels-to-your-documents-and-email-within-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
