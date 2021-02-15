---
title: HR 데이터를 미국 정부 클라우드로 가져오는 커넥터 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: 미국 정부 클라우드의 관리자는 데이터 커넥터를 설정하여 조직의 HR(인사) 시스템에서 Microsoft 365로 직원 데이터를 가져올 수 있습니다. 이렇게 하면 내부자 위험 관리 정책의 HR 데이터를 사용하여 조직에 내부 위협을 줄 수 있는 특정 사용자의 활동을 검색할 수 있습니다.
ms.openlocfilehash: 80998422eba32fe7f9118166f76a61d2d4bd8894
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619924"
---
# <a name="set-up-a-connector-to-import-hr-data-in-us-government"></a>미국 정부에서 HR 데이터를 가져오는 커넥터 설정

Microsoft 365 규정 준수 센터에서 데이터 커넥터를 설정하여 인사(HR) 데이터를 미국 정부 조직으로 가져올 수 있습니다. HR 관련 데이터에는 직원이 퇴사서를 제출한 날짜와 직원의 마지막 날이 포함됩니다. 그런 다음 내부자 위험 관리 솔루션과 같은 Microsoft [](insider-risk-management.md)정보 보호 솔루션에서 이 HR 데이터를 사용하여 조직 내부의 악의적인 활동이나 데이터 도용으로부터 조직을 보호할 수 있습니다. HR 커넥터 설정은 커넥터의 인증에 사용되는 Azure Active Directory에서 앱을 만들고, HR 데이터가 포함된 CSV 매핑 파일을 만들고, 준수 센터에서 데이터 커넥터를 만들고, CSV 파일의 HR 데이터를 Microsoft 클라우드로 수집하는 스크립트(예약된 기준)를 실행하는 것으로 구성됩니다. 그런 다음 내부자 위험 관리 도구에서 Microsoft 365 Government 조직으로 가져온 HR 데이터에 액세스하는 데 데이터 커넥터를 사용합니다.

## <a name="before-you-begin"></a>시작하기 전에

- 3단계에서 HR 커넥터를 만드는 사용자에게 Exchange Online에서 사서함 가져오기 내보내기 역할이 할당되어야 합니다. 기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다. Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다. 또는 새 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "Exchange [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) Online에서 [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서에서 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 참조하십시오.

- 조직의 HR 시스템에서 데이터를 검색하거나 내보내는 방법을 결정하고(정기적으로) 2단계에 설명된 CSV 파일에 추가해야 합니다. 4단계에서 실행한 스크립트는 CSV 파일의 HR 데이터를 Microsoft 클라우드에 업로드합니다.

- 4단계에서 실행한 샘플 스크립트는 내부자 위험 관리 솔루션과 같은 다른 Microsoft 도구에서 사용할 수 있도록 HR 데이터를 Microsoft 클라우드에 업로드합니다. 이 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서 지원되지 않습니다. 샘플 스크립트는 어떤 종류의 보증도 없이 그대로 제공됩니다. 또한 Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다. 샘플 스크립트 및 문서의 사용 또는 수행으로 인해 발생하는 모든 위험은 사용자의 책임입니다. 어떠한 경우에도 Microsoft, 스크립트 작성자 또는 그외 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용할 수 없음으로 인해 발생하는 모든 손해(수익 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알았더라도 마찬가지입니다.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>1단계: Azure Active Directory에서 앱 만들기

첫 번째 단계는 Azure AD(Azure Active Directory)에서 새 앱을 만들고 등록하는 것입니다. 앱은 3단계에서 만든 HR 커넥터에 해당합니다. 이 앱을 만들면 Azure AD가 실행될 때 HR 커넥터를 인증하고 조직에 액세스하려고 할 수 있습니다. 이 앱은 4단계에서 실행하여 HR 데이터를 Microsoft 클라우드에 업로드하는 데도 사용됩니다. 이 Azure AD 앱을 만들 때 다음 정보를 저장해야 합니다. 이러한 값은 이후 단계에서 사용됩니다.

- Azure AD 응용 프로그램 ID(앱 *ID* 또는 클라이언트 *ID라고도 합니다.)*

- Azure AD 응용 프로그램 비밀(클라이언트 *비밀이라고도 하는)*

- 테넌트 ID(디렉터리 *ID라고도 하는)*

Azure AD에서 앱을 만드는 단계별 지침은 Microsoft ID 플랫폼으로 응용 프로그램 [등록을 참조하세요.](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)

## <a name="step-2-prepare-a-csv-file-with-your-hr-data"></a>2단계: HR 데이터를 사용하여 CSV 파일 준비

다음 단계에서는 조직을 떠나는 직원에 대한 정보가 포함된 CSV 파일을 만들어야 합니다. 시작하기 전에 섹션에 설명된 경우 조직의 HR 시스템에서 이 CSV 파일을 생성하는 방법을 결정해야 합니다. 다음 예제에서는 3개의 필수 매개 변수(열)가 포함된 완료된 CSV 파일(메모장에서 열기)을 보여줍니다. Microsoft Excel에서 CSV 파일을 편집하는 것이 훨씬 쉽습니다.

```text
EmailAddress,TerminationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

CSV 파일의 첫 번째 행(머리줄 행)에는 필요한 열 이름이 나열됩니다. 각 열 헤더에 사용되는 이름은 사용자에 따라 지정됩니다(이전 예제의 이름은 제안 사항임). 그러나 3단계에서 HR 커넥터를 만들  때 CSV 파일에 사용하는 동일한 열 이름을 지정해야 합니다. 열 이름에 공백을 포함하지 않습니다.

다음 표에서는 CSV 파일의 각 열에 대해 설명합니다.

| 열 이름 | 설명 |
|:-----|:-----|
| **EmailAddress** <br/> |해지된 직원의 전자 메일 주소를 지정합니다.|
| **TerminationDate** <br/> |조직의 직원 고용이 공식적으로 종료된 날짜를 지정합니다. 예를 들어 이 날짜는 직원이 조직을 떠나는 것을 공지한 날짜일입니다. 이 날짜는 작업의 마지막 날과 다를 수 있습니다. `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)날짜 및 시간 형식인 날짜 형식을 사용 합니다.|
|**LastWorkingDate**|퇴사한 직원의 마지막 작업일을 지정합니다. `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm` [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html)날짜 및 시간 형식인 날짜 형식을 사용 합니다.|
|||

필요한 HR 데이터를 사용하여 CSV 파일을 만든 후 4단계에서 실행한 스크립트와 동일한 시스템에 저장합니다. CSV 파일에 항상 최신 정보가 포함될 수 있도록 업데이트 전략을 구현해야 합니다. 이렇게 하면 스크립트를 실행하면 최신 직원 종료 데이터가 Microsoft 클라우드에 업로드됩니다.

## <a name="step-3-create-the-hr-connector"></a>3단계: HR 커넥터 만들기

다음 단계는 Microsoft 365 규정 준수 센터에서 HR 커넥터를 만드는 것입니다. 4단계에서 스크립트를 실행하면 만든 HR 커넥터가 CSV 파일의 HR 데이터를 Microsoft 365 조직으로 수집합니다. 이 단계에서는 커넥터를 만들 때 생성되는 작업 ID를 복사해야 합니다. 스크립트를 실행할 때 작업 ID를 사용하게 됩니다.

1. Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and then click Data **connectors** in the left nav.

2. 데이터 커넥터 **페이지에서** **HR** 아래의 보기를 **클릭합니다.**

3. **HR 페이지에서** 커넥터 **추가를 클릭합니다.**

4. 인증 **자격 증명 페이지에서** 다음을 클릭하고 다음을 **클릭합니다.**

   1. 1단계에서 만든 Azure 앱의 Azure AD 응용 프로그램 ID를 입력하거나 붙여넣습니다.

   1. HR 커넥터의 이름을 입력합니다.

5. 파일 매핑 **페이지에서** 2단계에서 만든 CSV 파일의 세 열 머리더(매개 변수라고도 합니다.)의 이름을 각 해당 상자에 입력합니다.  이름은 대소문자 구분되지 않습니다. 앞서 설명한 것처럼 이러한 상자에 입력하는 이름은 CSV 파일의 매개 변수 이름과 일치해야 합니다. 예를 들어 다음 스크린샷은 2단계에 표시된 예제 CSV 파일의 예제에 있는 매개 변수 이름을 보여줍니다.

   ![열 제목 이름은 CSV 파일의 이름과 일치합니다.](../media/HRConnectorWizard3.png)

6. 검토 **페이지에서** 설정을 검토한 다음 **마친을** 클릭하여 커넥터를 만드십시오.

   커넥터가 만들어졌다는 확인을 확인하는 상태 페이지가 표시됩니다. 이 페이지에는 HR 데이터를 업로드하기 위해 샘플 스크립트를 실행하기 위해 다음 단계를 완료해야 하는 두 가지 중요한 정보가 포함되어 있습니다.

   ![작업 ID가 있는 검토 페이지 및 샘플 스크립트에 대한 github 링크](../media/HRConnector_Confirmation.png)

   1. **작업 ID입니다.** 다음 단계에서 스크립트를 실행하려면 이 작업 ID가 필요합니다. 이 페이지 또는 커넥터 플라이아웃 페이지에서 복사할 수 있습니다.
   
   1. **샘플 스크립트에 연결합니다.** 샘플 **스크립트에** 액세스하려면 다음 링크를 클릭하여 GitHub 사이트로 이동하세요(링크가 새 창 열립니다). 4단계에서 스크립트를 복사할 수 있도록 이 창을 열어 두십시오. 또는 4단계에서 다시 액세스할 수 있도록 대상에 책갈피를 지정하거나 URL을 복사할 수 있습니다. 이 링크는 커넥터 플라이아웃 페이지에서도 사용할 수 있습니다.

7. **완료** 를 클릭합니다.

   새 커넥터가 커넥터 탭의 목록에 **표시됩니다.** 

8. 방금 만든 HR 커넥터를 클릭하여 커넥터에 대한 속성 및 기타 정보가 포함된 플라이아웃 페이지를 표시합니다.

   ![새 HR 커넥터에 대한 플라이아웃 페이지](../media/HRConnectorWizard7.png)

   아직 수행하지 않은 경우 Azure 앱 ID 및 **커넥터** 작업 ID 값을 **복사할 수 있습니다.** 다음 단계에서 스크립트를 실행하려면 이러한 단계가 필요합니다. 플라이아웃 페이지에서 스크립트를 다운로드하거나 다음 단계의 링크를 사용하여 다운로드할 수도 있습니다.

   편집을 **클릭하여** 파일 매핑 페이지에 정의한 Azure 앱 ID 또는 열 헤더 이름을 변경할 **수도** 있습니다.

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>4단계: 샘플 스크립트를 실행하여 HR 데이터 업로드

HR 커넥터를 설정하는 마지막 단계는 CSV 파일의 HR 데이터(2단계에서 만든)를 Microsoft 클라우드에 업로드하는 샘플 스크립트를 실행하는 것입니다. 특히 스크립트는 데이터를 HR 커넥터에 업로드합니다. 스크립트를 실행한 후 3단계에서 만든 HR 커넥터는 HR 데이터를 Microsoft 365 조직으로 가져와 내부자 위험 관리 솔루션과 같은 다른 규정 준수 도구에서 액세스할 수 있습니다. 스크립트를 실행한 후 가장 최근 직원 종료 데이터가 Microsoft 클라우드에 업로드될 수 있도록 매일 자동으로 실행되는 작업을 계획하는 것이 좋습니다. 스크립트가 [자동으로 실행될 예약을 참조합니다.](#optional-step-6-schedule-the-script-to-run-automatically)

1. 이전 단계에서 열린 창으로 이동하여 샘플 스크립트를 사용하여 GitHub 사이트에 액세스합니다. 또는 책갈피로 지정한 사이트를 열거나 복사한 URL을 사용합니다.

2. 원시  단추를 클릭하여 텍스트 보기에 스크립트를 표시합니다.

3. 샘플 스크립트의 모든 줄을 복사한 다음 텍스트 파일에 저장합니다.

4. 필요한 경우 조직의 샘플 스크립트를 수정합니다.

5. 파일 이름 접미사로 텍스트 파일을 Windows PowerShell 파일로 `.ps1` `HRConnector.ps1` 저장합니다.

6. 로컬 컴퓨터에서 명령 프롬프트를 열고 스크립트를 저장한 디렉터리로 이동하십시오.

7. 다음 명령을 실행하여 CSV 파일의 HR 데이터를 Microsoft 클라우드에 업로드합니다. 예를 들어:

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   다음 표에서는 이 스크립트와 함께 사용할 매개 변수와 필요한 값에 대해 설명합니다. 이전 단계에서 얻은 정보는 이러한 매개 변수의 값에 사용됩니다.

   | 매개 변수 | 설명 |
   |:-----|:-----|:-----|
   |`tenantId`|1단계에서 획득한 Microsoft 365 조직의 ID입니다. Azure AD 관리 센터의 개요 블레이드에서  조직의 테넌트 ID를 얻을 수도 있습니다. 이는 조직을 식별하는 데 사용됩니다.|
   |`appId` |1단계에서 Azure AD에서 만든 앱의 Azure AD 응용 프로그램 ID입니다. 스크립트가 Microsoft 365 조직에 액세스하려고 할 때 Azure AD에서 인증에 사용됩니다. |
   |`appSecret`|1단계에서 Azure AD에서 만든 앱에 대한 Azure AD 응용 프로그램 비밀입니다. 이는 인증에도 사용됩니다.|
   |`jobId`|3단계에서 만든 HR 커넥터의 작업 ID입니다. 이 데이터는 Microsoft 클라우드에 업로드된 HR 데이터를 HR 커넥터와 연결하기 위해 사용됩니다.|
   |`csvFilePath`|2단계에서 만든 CSV 파일의 파일 경로(스크립트와 동일한 시스템에 저장) 파일 경로의 공백을 방지합니다. 그렇지 않으면 인용 부호를 하나만 사용할 수 있습니다.|
   |||
   
   다음은 각 매개 변수에 실제 값을 사용하는 HR 커넥터 스크립트 구문의 예입니다.

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   업로드가 성공하면 스크립트에 성공한 업로드 **메시지가** 표시됩니다.

   > [!NOTE]
   > 실행 정책으로 인하여 이전 명령을 실행하는 [](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_execution_policies) 데 문제가 있는 경우 실행 정책 설정에 대한 지침은 실행 정책 및 [Set-ExecutionPolicy를](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy) 참조하세요.

## <a name="step-5-monitor-the-hr-connector"></a>5단계: HR 커넥터 모니터링

HR 커넥터를 만들고 스크립트를 실행하여 HR 데이터를 업로드한 후 Microsoft 365 규정 준수 센터에서 커넥터를 보고 상태를 업로드할 수 있습니다. 정기적으로 스크립트가 자동으로 실행될 예정인 경우 스크립트가 마지막으로 실행된 후 현재 상태를 볼 수도 있습니다.

1. Go to [https://compliance.microsoft.com](https://compliance.microsoft.com) and click **Data connectors** in the left nav.

2. 커넥터 **탭을** 클릭한 다음 HR 커넥터를 선택하여 플라이아웃 페이지를 표시합니다. 이 페이지에는 커넥터에 대한 속성과 정보가 포함되어 있습니다.

   ![속성 및 상태가 있는 HR 커넥터 플라이아웃 페이지](../media/HRConnectorFlyout1.png)

3. 진행 **중일** 때 로그 다운로드 **링크를** 클릭하여 커넥터의 상태 로그를 열거나 저장합니다. 이 로그에는 스크립트를 실행하고 CSV 파일의 데이터를 Microsoft 클라우드로 업로드할 때마다 대한 정보가 포함되어 있습니다. 

   ![HR 커넥터 로그 파일에 업로드된 CSV 파일의 숫자 행이 표시됩니다.](../media/HRConnectorLogFile.png)

   이 `RecordsSaved` 필드는 업로드한 CSV 파일의 행 수를 나타냅니다. 예를 들어 CSV 파일에 네 개의 행이 포함되어 있는 경우 스크립트가 CSV 파일의 모든 행을 업로드한 경우 필드 값은 `RecordsSaved` 4입니다.

4단계에서 스크립트를 실행하지 않은 경우 마지막 가져오기 아래에 스크립트 다운로드 **링크가 표시됩니다.** 스크립트를 다운로드한 다음 4단계의 단계에 따라 스크립트를 실행할 수 있습니다.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(선택 사항) 6단계: 스크립트를 자동으로 실행 예약

조직의 최신 HR 데이터를 내부자 위험 관리 솔루션과 같은 도구에서 사용할 수 있도록 1일 1회와 같이 스크립트가 정기적으로 실행되는 것을 예약하는 것이 좋습니다. 이렇게 하려면 조직을 떠나는 직원에 대한 최신 정보를 포함하기 위해 CSV 파일의 HR 데이터를 유사한 일정(같지 않은 경우)으로 업데이트해야 합니다. 목표는 내부자 위험 관리 솔루션에서 HR 커넥터를 사용할 수 있도록 가장 최근의 HR 데이터를 업로드하는 것입니다.

Windows에서 작업 스케줄러 앱을 사용하여 매일 스크립트를 자동으로 실행할 수 있습니다.

1. 로컬 컴퓨터에서 **Windows** 시작 단추를 클릭한 다음 작업 스케줄러를 **입력합니다.**

2. 작업 **스케줄러 앱을 클릭하여** 열립니다.

3. 작업 **섹션에서** 작업 **만들기를 클릭합니다.**

4. 일반 **탭에서** 예약된 작업에 대한 설명적인 이름을 입력합니다. 예: **HR 커넥터 스크립트.** 선택적 설명을 추가할 수도 있습니다.

5. 보안 **옵션에서** 다음을 합니다.

   1. 컴퓨터에 로그온할 때만 스크립트를 실행할지, 로그온할 때 스크립트를 실행할지 여부를 결정하십시오.
   
   1. 가장 높은 권한으로 **실행 확인란이** 선택되어 있는지 확인 합니다.

6. 트리거 **탭을** 선택하고 새로 고치고 다음을 실행합니다.

   1. **설정에서** 일별  옵션을 선택한 다음 스크립트를 처음으로 실행할 날짜와 시간을 선택합니다. 스크립트는 매일 같은 지정된 시간으로 실행됩니다.
   
   1. 고급 **설정에서** 사용 **확인란이** 선택되어 있는지 확인합니다.
   
   1. 확인을 **클릭합니다.**

7. 작업 **탭을** 선택하고 새로 고치고 다음을 수행하십시오.

   ![HR 커넥터 스크립트에 대해 예약된 새 작업을 만들기 위한 작업 설정](../media/HRConnectorScheduleTask1.png)

   1. 작업 **드롭다운** 목록에서 프로그램 **시작이 선택되어** 있는지 확인 합니다.

   1. **프로그램/스크립트** 상자에서 찾아보기를 클릭하고 다음 위치로 이동하여 경로를 상자에 표시하려면  `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe` 선택합니다.

   1. 인수 **추가(선택 사항)** 상자에 4단계에서 실행한 동일한 스크립트 명령을 붙여 넣습니다. 예를 들어 `.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   1. 시작 **위치(선택 사항)** 상자에 4단계에서 실행한 스크립트의 폴더 위치를 붙여 넣습니다. 예를 들면 `C:\Users\contosoadmin\Desktop\Scripts`와 같습니다.

   1. **확인을** 클릭하여 새 작업의 설정을 저장합니다.

8. 작업 만들기 **창에서** 확인을 **클릭하여** 예약된 작업을 저장합니다. 사용자 계정 자격 증명을 입력하라는 메시지가 표시될 수 있습니다.

   새 작업이 작업 스케줄러 라이브러리에 표시됩니다.

   ![작업 스케줄러 라이브러리에 새 작업이 표시됩니다.](../media/HRConnectorTaskSchedulerLibrary.png)

   스크립트가 마지막으로 실행된 시간 및 다음에 실행이 예약될 때 표시됩니다. 작업을 두 번 클릭하여 편집할 수 있습니다.

   또한 준수 센터에서 해당 HR 커넥터의 플라이아웃 페이지에서 스크립트가 마지막으로 실행된 시간을 확인할 수도 있습니다.
