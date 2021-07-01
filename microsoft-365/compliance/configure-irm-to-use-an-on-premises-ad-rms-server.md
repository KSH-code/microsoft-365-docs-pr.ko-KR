---
title: 온-프레미스 AD RMS 서버를 사용하도록 IRM 구성
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/13/2017
audience: End User
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 3ecde857-4b7c-451d-b4aa-9eeffc8a8c61
ms.collection:
- M365-security-compliance
description: AD RMS(Active Directory Rights Management Service) 서버를 사용하도록 Exchange Online IRM(정보 권한 관리)을 구성하는 방법을 확인합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2c42d793639a9efaf94e3222a172ea192d1e03d3
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/30/2021
ms.locfileid: "53227238"
---
# <a name="configure-irm-to-use-an-on-premises-ad-rms-server"></a>온-프레미스 AD RMS 서버를 사용하도록 IRM 구성

Exchange Online Server 2008 이상의 정보 보호 기술인 AD RMS(Active Directory Rights Management Services(정보 권한 관리)를 Windows 배포에 사용할 수 있습니다. AD RMS 권한 정책 템플릿을 전자 메일 메시지에 적용하여 전자 메일에 IRM 보호를 적용합니다. 조직 방화벽 내부와 외부에서 온라인 및 오프라인으로 보호가 진행할 수 있도록 메시지 자체에 권한이 첨부됩니다.

이 항목에서는 AD RMS 서버를 사용하도록 IRM을 구성하는 방법을 보여줍니다. Office 365 메시지 암호화 및 Azure 권한 관리에서 새 기능을 Azure Active Directory 대한 자세한 내용은 Office 365 메시지 암호화 [FAQ를 참조하세요.](./ome-faq.yml)

Exchange Online의 IRM에 대한 자세한 내용은 [Information Rights Management in Exchange Online](information-rights-management-in-exchange-online.md)를 참조하십시오.

## <a name="what-do-you-need-to-know-before-you-begin"></a>시작하기 전에 알아야 할 내용

- 이 작업의 예상 완료 시간: 30분

- 이러한 절차를 수행하려면 먼저 사용 권한을 할당받아야 합니다. 필요한 사용 권한을 표시하려면 메시징 정책 및 규정 준수 권한 항목의 "정보 권한 관리" [항목을 참조하세요.](/Exchange/permissions/feature-permissions/policy-and-compliance-permissions)

- AD RMS 서버에서 Windows Server 2008 이상이 실행되고 있어야 합니다. AD RMS를 배포하는 방법에 대한 자세한 내용은 [AD RMS 클러스터 설치를 참조하세요.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc726041(v=ws.11))

- Windows PowerShell을 설치 및 구성하고 서비스에 연결하는 방법에 대한 자세한 내용은 [Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하십시오.

- 이 항목의 절차에 적용할 수 있는 바로 가기 키에 대한 자세한 내용은 Exchange 관리 센터의 바로 가기 키를 [Exchange Online.](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> 문제가 있습니까? Exchange 포럼에서 도움을 요청하세요. 포럼 주소는 다음과 같습니다.[Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542), 또는 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351)

## <a name="how-do-you-do-this"></a>어떻게 해야 합니까?
<a name="sectionSection1"> </a>

### <a name="step-1-use-the-ad-rms-console-to-export-a-trusted-publishing-domain-tpd-from-an-ad-rms-server"></a>1단계: AD RMS 콘솔을 사용하여 AD RMS 서버에서 TPD(트러스트된 게시 도메인)를 내보냅니다.

첫 번째 단계는 온-프레미스 AD RMS 서버의 TPD(트러스트된 게시 도메인)를 XML 파일로 내보내는 것입니다. TPD에는 RMS 기능을 사용하는 데 필요한 다음과 같은 설정이 포함됩니다.

- 인증서 및 라이선스 서명 및 암호화에 사용되는 SLC(서버 사용 허가자 인증서)

- 라이선스 및 게시에 사용되는 URL

- 해당 TPD에 대한 특정 SLC로 만들어진 AD RMS 권한 정책 템플릿

TPD를 가져오면 TPD가 저장되고 TPD에 Exchange Online.

1. Active Directory Rights Management Services 콘솔을 연 다음 AD RMS 클러스터를 확장합니다.

2. 콘솔 트리에서 **트러스트 정책** 을 확장한 다음 **트러스트된 게시 도메인** 을 클릭합니다.

3. 결과 창에서 내보낼 도메인에 대한 인증서를 선택합니다.

4. **작업** 창에서 **트러스트된 게시 도메인 내보내기** 를 클릭합니다.

5. **게시 도메인 파일** 상자에서 **다른 이름으로 저장** 을 클릭하여 파일을 로컬 컴퓨터의 특정 위치에 저장합니다. 파일 이름을 입력하고 파일 이름 확장명을 지정한 다음 `.xml` 저장을 **클릭합니다.**

6. **암호** 및 **암호 확인** 상자에 트러스트된 게시 도메인 파일을 암호화하는 데 사용할 강력한 암호를 입력합니다. TPD를 클라우드 기반 전자 메일 조직으로 가져올 때 이 암호를 지정해야 합니다.

### <a name="step-2-use-the-exchange-management-shell-to-import-the-tpd-to-exchange-online"></a>2단계: Exchange 관리 셸을 사용하여 TPD를 Exchange Online

TPD를 XML 파일로 내보낸 후에는 Exchange Online으로 가져와야 합니다. TPD를 가져오면 조직의 AD RMS 템플릿도 가져오게 됩니다. 첫 번째 TPD를 가져오면 해당 TPD가 클라우드 기반 조직에 대한 기본 TPD가 됩니다. 다른 TPD를 가져오는 경우 **Default** 스위치를 사용하여 TPD를 사용자가 사용할 수 있는 기본 TPD로 만들 수 있습니다.

TPD를 가져오려면 Windows PowerShell에서 다음 명령을 실행합니다.

```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path <path to exported TPD file> -ReadCount 0)) -Name "<name of TPD>" -ExtranetLicensingUrl <URL> -IntranetLicensingUrl <URL>
```

추가 콘솔에서 _ExtranetLicensingUrl_ 및 _IntranetLicensingUrl_ 매개 변수의 값을 Active Directory Rights Management Services 있습니다. 콘솔 트리에서 AD RMS 클러스터를 선택합니다. 라이선스 URL이 결과 창에 표시됩니다. 이러한 URL은 콘텐츠의 암호를 해제해야 하는 경우와 Exchange Online에서 사용할 TPD를 결정해야 하는 경우 전자 메일 클라이언트가 사용합니다.

이 명령을 실행하면 암호를 입력하라는 메시지가 표시될 수 있습니다. AD RMS 서버에서 TPD를 내보낼 때 지정한 암호를 입력합니다.

예를 들어 다음 명령은 AD RMS 서버에서 내보내고 관리자 계정의 바탕 화면에 저장한 XML 파일을 사용하여 이름이 Exported TPD라는 TPD를 가져옵니다. Name 매개 변수를 사용하여 TPD에 이름을 지정합니다.

```powershell
Import-RMSTrustedPublishingDomain -FileData $([byte[]](Get-Content -Encoding byte -Path C:\Users\Administrator\Desktop\ExportTPD.xml -ReadCount 0)) -Name "Exported TPD" -ExtranetLicensingUrl https://corp.contoso.com/_wmcs/licensing -IntranetLicensingUrl https://rmsserver/_wmcs/licensing
```

구문과 매개 변수에 대한 자세한 내용은 [Import-RMSTrustedPublishingDomain](/powershell/module/exchange/import-rmstrustedpublishingdomain)을 참조하십시오.

#### <a name="how-do-you-know-this-step-worked"></a>이 단계의 작동 여부는 어떻게 확인합니까?

TPD를 가져왔다는 것을 확인하기 위해 **Get-RMSTrustedPublishingDomain** cmdlet을 실행하여 조직에서 TPD를 Exchange Online 합니다. 자세한 내용은 [Get-RMSTrustedPublishingDomain](/powershell/module/exchange/get-rmstrustedpublishingdomain)의 예를 참조하십시오.

### <a name="step-3-use-the-exchange-management-shell-to-distribute-an-ad-rms-rights-policy-template"></a>3단계: Exchange 관리 셸을 사용하여 AD RMS 권한 정책 템플릿 배포

TPD를 가져온 후 AD RMS 권한 정책 템플릿이 배포되어 있는지 확인해야 합니다. 배포된 서식 파일은 웹용 Outlook(Outlook Web App) 사용자에게 표시되어 전자 메일 메시지에 서식 파일을 적용할 수 있습니다.

기본 TPD에 포함된 모든 템플릿 목록을 반환하려면 다음 명령을 실행합니다.

```powershell
Get-RMSTemplate -Type All | fl
```

Type 매개 변수의  _값이 인_ 경우 템플릿이 사용자에게  `Archived` 표시되지 않습니다. 기본 TPD의 분산된 템플릿만 기본 TPD에서 사용할 수 웹용 Outlook.

템플릿을 배포하려면 다음 명령을 실행합니다.

```powershell
Set-RMSTemplate -Identity "<name of the template>" -Type Distributed
```

예를 들어 다음 명령은 Company Confidential 템플릿을 가져옵니다.

```powershell
Set-RMSTemplate -Identity "Company Confidential" -Type Distributed
```

구문과 매개 변수에 대한 자세한 내용은 [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate) 및 [Set-RMSTemplate](/powershell/module/exchange/set-rmstemplate)을 참조하십시오.

**전달하지 않음 템플릿**

온-프레미스 조직의 기본 TPD를 Exchange Online으로 가져올 때 **전달하지 않음** 이라는 하나의 AD RMS 권한 정책 템플릿을 가져옵니다. 이 템플릿은 기본 TPD를 가져올 때 기본적으로 배포됩니다. **Set-RMSTemplate** cmdlet을 사용하여 **전달하지 않음** 템플릿을 수정할 수 없습니다.

**전달하지 않음** 템플릿이 메시지에 적용되면 메시지에 주소가 지정되어 있는 받는 사람만 메시지를 읽을 수 있습니다. 또한 받는 사람은 다음을 수행할 수 없습니다.

- 다른 사람에게 메시지를 전달합니다.

- 메시지의 내용을 복사합니다.

- 메시지를 인쇄합니다.

> [!IMPORTANT]
> **전달하지 않음** 템플릿을 사용하는 경우 메시지의 정보가 수동으로 정보를 기록하는 타사 화면 캡처 프로그램, 카메라 또는 사용자에게 복사되지 않도록 할 수 없습니다.

온-프레미스 조직의 AD RMS 서버에 AD RMS 권한 정책 템플릿을 추가로 만들어 IRM 보호 요구 사항을 충족할 수 있습니다. AD RMS 권한 정책 템플릿을 추가로 만들 경우 다시 온-프레미스 AD RMS 서버에서 TPD를 내보낸 후 클라우드 기반 전자 메일 조직에서 해당 TPD를 새로 고쳐야 합니다.

#### <a name="how-do-you-know-this-step-worked"></a>이 단계의 작동 여부는 어떻게 확인합니까?

AD RMS 권한 정책 템플릿을 성공적으로 배포하고 있는지 확인하기 위해 **Get-RMSTemplate** cmdlet을 실행하여 템플릿의 속성을 검사합니다. 자세한 내용은 [Get-RMSTemplate](/powershell/module/exchange/get-rmstemplate)의 예를 참조하십시오.

### <a name="step-4-use-the-exchange-management-shell-to-enable-irm"></a>4단계: Exchange 관리 셸을 사용하여 IRM을 사용하도록 설정

TPD를 가져오고 AD RMS 권한 정책 템플릿을 배포했으면 다음 명령을 실행하여 클라우드 기반 전자 메일 조직에 대해 IRM을 사용하도록 설정합니다.

```powershell
Set-IRMConfiguration -InternalLicensingEnabled $true
```

구문과 매개 변수에 대한 자세한 내용은 [Set-IRMConfiguration](/powershell/module/exchange/set-irmconfiguration)를 참조하십시오.

#### <a name="how-do-you-know-this-step-worked"></a>이 단계의 작동 여부는 어떻게 확인합니까?

IRM이 사용하도록 설정되어 있는지 확인하려면 [Get-IRMConfiguration](/powershell/module/exchange/get-irmconfiguration) cmdlet을 실행하여 조직에서 IRM Exchange Online 확인합니다.

## <a name="how-do-you-know-this-task-worked"></a>이 작업의 작동 여부는 어떻게 확인하나요?
<a name="sectionSection2"> </a>

TPD를 가져오고 IRM을 사용하도록 설정했는지 확인하려면 다음을 수행합니다.

- **Test-IRMConfiguration** cmdlet을 사용하여 IRM 기능을 테스트합니다. 자세한 내용은 [Test-IRMConfiguration의](/powershell/module/exchange/test-irmconfiguration)"예제 1"을 참조합니다.

- 확장된 메뉴에서 웹용 Outlook 설정 옵션을 선택하여 새 메시지를 작성하고 IRM으로 보호합니다. 확장 메뉴(추가 옵션  ![ 아이콘)에서 사용 권한 설정 옵션을 선택합니다. ](../media/ITPro-EAC-MoreOptionsIcon.gif)
