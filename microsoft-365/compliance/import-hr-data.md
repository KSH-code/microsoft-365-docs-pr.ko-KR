---
title: HR 데이터를 가져올 커넥터 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: 관리자는 조직의 HR (인적 자원) 시스템에서 직원 데이터를 Microsoft 365로 가져오는 데이터 커넥터를 설정할 수 있습니다. 이를 통해 참가자 위험 관리 정책에 HR 데이터를 사용 하 여 조직에 내부적인 위협을 초래할 수 있는 특정 사용자의 작업을 검색 하는 데 도움을 받을 수 있습니다.
ms.openlocfilehash: 4b01571d5a56d53861481dac6cb399e227ca0db6
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42073040"
---
# <a name="set-up-a-connector-to-import-hr-data"></a>HR 데이터를 가져올 커넥터 설정

Microsoft 365 준수 센터에서 데이터 커넥터를 설정 하 여 직원 들이 직원의 resignation 및 날짜를 제출한 날짜와 같은 HR (인적 자원) 데이터를 가져올 수 있습니다. 이 HR 데이터는 새로운 [참가자 위험 관리 솔루션과](insider-risk-management.md)같은 Microsoft 정보 보호 솔루션에서 조직의 악의적인 활동 또는 데이터 절도 로부터 조직을 보호 하는 데 도움이 될 수 있습니다. HR 커넥터를 설정 하는 작업은 커넥터를 통한 인증에 사용 되는 Azure Active Directory의 앱을 만들고, HR 데이터를 포함 하는 CSV 매핑 파일을 만들고, 준수 센터에서 데이터 커넥터를 만든 다음 스크립트를 실행 하는 작업입니다. 예약 된 방식) CSV 파일의 HR 데이터를 Microsoft 클라우드로 ingests. 그런 다음 데이터 커넥터를 사용 하 여 microsoft 365 조직으로 가져온 HR 데이터에 액세스 하는 데에는 insider 위기 관리 등의 Microsoft 규정 준수 솔루션입니다.

## <a name="before-you-begin"></a>시작하기 전에

- 조직에서는 Office 365 가져오기 서비스가 조직의 데이터에 액세스 하도록 허용 하는 데 동의 해야 합니다. 이 요청에 동의 하려면 [이 페이지로](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)이동 하 여 Microsoft 365 전역 관리자의 자격 증명으로 로그인 한 다음 요청을 수락 합니다. 3 단계에서 HR 커넥터를 성공적으로 만들기 전에이 단계를 완료 해야 합니다.

- 3 단계에서 HR 커넥터를 만드는 사용자에 게 Exchange Online의 사서함 가져오기 내보내기 역할이 할당 되어야 합니다. 기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다. Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다. 또는 새 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당 한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "Exchange Online에서 역할 그룹 관리" 문서의 [역할 그룹 만들기](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 또는 [역할 그룹 수정](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 섹션을 참조 하세요.

- 조직의 HR 시스템에서 데이터를 검색 하거나 내보내는 방법 (정기적으로)을 결정 하 고 2 단계에서 설명 하는 CSV 파일에 추가 하는 방법을 확인 해야 합니다. 4 단계에서 실행 하는 스크립트는 CSV 파일의 HR 데이터를 Microsoft 클라우드에 업로드 합니다.

- 4 단계에서 실행 하는 예제 스크립트는 참가자 위험 관리 솔루션과 같은 다른 Microsoft 도구에서 사용할 수 있도록 HR 데이터를 Microsoft 클라우드에 업로드 합니다. 이 샘플 스크립트는 Microsoft standard 지원 프로그램 또는 서비스에서 지원 되지 않습니다. 예제 스크립트는 어떤 종류의 보증도 없이 있는 그대로 제공 됩니다. Microsoft는 상품성 또는 특정 목적에 대 한 적합성에 대 한 묵시적 보증을 제한 없이 포함 하 여 모든 묵시적 보증을 배제 합니다. 샘플 스크립트 및 설명서의 사용 또는 성능으로 인해 발생 하는 전체 위험은 사용자에 게 남아 있습니다. Microsoft, 작성자 또는 스크립트를 작성, 프로덕션 또는 전달 하는 것과 관련 된 다른 모든 손해에 대 한 책임 (예를 들어, 비즈니스 이익 손실에 대 한 손해, 비즈니스 중단 Microsoft에서 이러한 손해에 대 한 권고를 받은 경우에도 예제 스크립트나 설명서를 사용 하거나 사용 하지 못하는 등의 비즈니스 정보 또는 기타 pecuniary 손실입니다.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>1 단계: Azure Active Directory에 앱 만들기

첫 번째 단계는 AAD (Azure Active Directory)에서 새 앱을 만들고 등록 하는 것입니다. 이 앱은 3 단계에서 만든 HR 커넥터에 해당 합니다.  이 앱을 만들면 AAD에서 HR 커넥터를 실행 하 여 조직에 액세스 하려고 할 때 인증을 받을 수 있습니다. 이 앱은 Microsoft 클라우드로 HR 데이터를 업로드 하는 4 단계에서 실행 하는 스크립트를 인증 하는 데에도 사용 됩니다. 이 AAD 앱을 만드는 동안 다음 정보를 저장 해야 합니다. 이러한 값은 이후 단계에서이 프로세스에 사용 됩니다.

- AAD 응용 프로그램 ID ( *앱 id* 또는 *클라이언트 ID*라고도 함)

- AAD 응용 프로그램 비밀 ( *클라이언트 암호*라고도 함)

- 테 넌 트 Id ( *디렉터리 Id*라고도 함)

AAD에서 앱을 만드는 단계별 지침은 [Aad 응용 프로그램 만들기](https://docs.microsoft.com/azure/kusto/management/access-control/how-to-provision-aad-app) 를 참조 하세요.

## <a name="step-2-prepare-a-csv-file-with-your-hr-data"></a>2 단계: HR 데이터를 사용 하 여 CSV 파일 준비

다음 단계에서는 조직에서 떠난 직원에 대 한 정보가 포함 된 CSV 파일을 만듭니다. 시작 하기 전에 섹션에서 설명한 것 처럼 조직의 HR 시스템에서이 CSV 파일을 생성 하는 방법을 결정 해야 합니다. 다음 예제에서는 세 개의 필수 매개 변수 (열)를 포함 하는 완성 된 CSV 파일 (메모장에서 열림)을 보여 줍니다. Microsoft Excel에서 CSV 파일을 편집 하는 것이 훨씬 더 쉽습니다.

```text
EmailAddress,TerminationDate,LastWorkingDate
sarad@contoso.com,2019-04-23T15:18:02.4675041+05:30,2019-04-29T15:18:02.4675041+05:30
pilarp@contoso.com,2019-04-24T09:15:49Z,2019-04-29T15:18:02.7117540
```

CSV 파일의 첫 번째 행 또는 머리글 행에는 필요한 열 이름이 나열 됩니다. 각 열 머리글에 사용 되는 이름은 사용자에 게 표시 됩니다 (이전 예의 제안). 그러나 3 단계에서 HR 커넥터를 만들 때 CSV 파일에서 사용 하는 것과 동일한 열 이름을 지정 *해야 합니다* . 열 이름에 공백을 포함 하지 않습니다.

다음 표에는 CSV 파일의 각 열에 대 한 설명이 나와 있습니다.

|**열 이름**|**설명**|
|:-----|:-----|
| **EmailAddress** <br/> |종료 된 직원의 전자 메일 주소를 지정 합니다.|
| **TerminationDate** <br/> |조직의 직원이 공식적으로 종료 된 날짜를 지정 합니다. 예를 들어 직원에 게 조직 내 상태에 대 한 알림이 제공 된 날짜를 예로 들 수 있습니다. 이 날짜는 사용자가 마지막으로 작업 한 날짜와 다를 수 있습니다. [ISO 8601 날짜 및 시간 형식인](https://www.iso.org/iso-8601-date-and-time-format.html)와 `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm`같은 날짜 형식을 사용 해야 합니다.|
|**LastWorkingDate**|종료 된 직원에 대 한 마지막 작업 날짜를 지정 합니다. [ISO 8601 날짜 및 시간 형식인](https://www.iso.org/iso-8601-date-and-time-format.html)와 `yyyy-mm-ddThh:mm:ss.nnnnnn+|-hh:mm`같은 날짜 형식을 사용 해야 합니다.|
|||

필요한 HR 데이터로 CSV 파일을 만든 후에는 4 단계에서 스크립트를 실행 하는 로컬 컴퓨터에 저장 합니다. 또한 스크립트를 실행 하는 데 필요한 모든 정보를 Microsoft 클라우드에 업로드 하기 위해 CSV 파일에 항상 최신 정보가 포함 되도록 하기 위해 업데이트 전략을 구현 해야 합니다.

## <a name="step-3-create-the-hr-connector"></a>3 단계: HR 커넥터 만들기

다음 단계는 Microsoft 365 준수 센터에서 HR 커넥터를 만드는 것입니다. 4 단계에서 스크립트를 실행 하면 사용자가 만든 HR 커넥터가 CSV 파일의 HR 데이터를 Microsoft 365 조직으로 수집 합니다. 이 단계에서는 커넥터를 만들 때 생성 되는 JobId를 복사 해야 합니다. 스크립트를 실행할 때 JobId를 사용 합니다.

1. 로 이동한 [https://compliance.microsoft.com](https://compliance.microsoft.com) 후 왼쪽 탐색 창에서 **데이터 커넥터** 를 클릭 합니다.

2. **데이터 커넥터 (미리 보기)** 페이지의 **HR**에서 **보기**를 클릭 합니다.

3. **HR** 페이지에서 **커넥터 추가**를 클릭 합니다.

4. **인증 자격 증명** 페이지에서 다음을 수행한 후 **다음**을 클릭 합니다.

   a. 1 단계에서 만든 Azure 앱에 대 한 AAD 응용 프로그램 ID를 입력 하거나 붙여넣습니다.

   b. HR 커넥터의 이름을 입력 합니다.

5. **파일 매핑** 페이지에서 열 머리글 이름 3 개 (해당 하는 각 상자에 2 단계에서 만든 CSV 파일의 *매개 변수* 라고도 함)를 입력 합니다. 이름은 대/소문자를 구분 하지 않습니다. 앞에서 설명한 것 처럼 이러한 상자에 입력 하는 이름은 CSV 파일의 매개 변수 이름과 일치 해야 합니다. 예를 들어 다음 스크린샷에서는 2 단계에 표시 된 예제 CSV 파일 예제에 나와 있는 매개 변수 이름을 보여 줍니다.

   ![열 머리글 이름이 CSV 파일의 이름과 일치 합니다.](../media/HRConnectorWizard3.png)

6. **검토** 페이지에서 설정을 검토 하 고 **마침을** 클릭 하 여 커넥터를 만듭니다.

   커넥터를 만들었는지 확인 하는 상태 페이지가 표시 됩니다. 이 페이지에는 작업 ID도 포함 되어 있습니다. 다음 단계에서 스크립트를 실행 하려면이 작업 ID가 필요 합니다. 이 페이지 또는 커넥터의 플라이 아웃 페이지에서이를 복사할 수 있습니다.

7. **완료**를 클릭합니다.
   
   새 커넥터가 **커넥터** 탭의 목록에 표시 됩니다. 

8. 방금 만든 HR 커넥터를 클릭 하 여 커넥터에 대 한 속성 및 기타 정보를 포함 하는 플라이 아웃 페이지를 표시 합니다. 

   ![새 HR 커넥터에 대 한 플라이 아웃 페이지](../media/HRConnectorWizard7.png)

   아직 수행 하지 않은 경우 **Azure 앱 id** 및 **커넥터 작업 id**의 값을 복사할 수 있습니다. 스크립트를 실행 하려면 다음 단계에서이를 수행 해야 합니다. 또한 플라이 아웃 페이지에서 스크립트를 다운로드 하거나 다음 단계에 있는 링크를 사용 하 여 다운로드할 수 있습니다.

   **편집** 을 클릭 하 여 AZURE 앱 ID 또는 **파일 매핑** 페이지에서 정의한 열 머리글 이름을 변경할 수도 있습니다.

## <a name="step-4-run-the-sample-script-to-upload-your-hr-data"></a>4 단계: 예제 스크립트를 실행 하 여 HR 데이터 업로드

HR 커넥터를 설정 하는 마지막 단계는 2 단계에서 만든 CSV 파일의 HR 데이터를 Microsoft 클라우드에 업로드 하는 예제 스크립트를 실행 하는 것입니다. 특히 스크립트는 데이터를 HR 커넥터에 업로드 합니다. 스크립트를 실행 하면 3 단계에서 만든 HR 커넥터가 Microsoft 365 조직에 게 HR 데이터를 가져오고,이는 참가자 위험 관리 솔루션과 같은 다른 규정 준수 도구에서 액세스할 수 있습니다. 스크립트를 실행 한 후에는 가장 최근 직원 종료 데이터가 Microsoft 클라우드에 업로드 되도록 매일 자동으로 실행 되는 작업을 예약 하는 것이 좋습니다. [스크립트를 자동으로 실행 하도록 예약을](#optional-step-6-schedule-the-script-to-run-automatically)참조 하십시오.

1. [이 GitHub 사이트로](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1) 이동 하 여 예제 스크립트에 액세스 합니다.

2. **Raw** 단추를 클릭 하 여 스크립트를 텍스트 보기로 표시 합니다.

3. 예제 스크립트의 모든 줄을 복사한 다음 텍스트 파일에 저장 합니다.

4. 필요한 경우 조직에 대 한 예제 스크립트를 수정 합니다.

5. 파일 이름 접미사를 사용 하 여 Windows PowerShell 스크립트 파일로 텍스트 파일을 저장 합니다 `.ps1`. 예를 `HRConnector.ps1`들면입니다.

6. 로컬 컴퓨터에서 명령 프롬프트를 열고 스크립트를 저장 한 디렉터리로 이동 합니다.

7. 다음 명령을 실행 하 여 CSV 파일의 HR 데이터를 Microsoft 클라우드에 업로드 합니다. 예를 들어:

    ```powershell
    .\HRConnector.ps1 -tenantId <tenantId> -appId <appId>  -appSecret <appSecret>  -jobId <jobId>  -csvFilePath '<csvFilePath>'
    ```

   다음 표에서는이 스크립트와 함께 사용 하는 매개 변수와 해당 필수 값에 대해 설명 합니다. 위의 단계에서 얻은 정보는 이러한 매개 변수의 값에 사용 됩니다.

   |**매개 변수**|**설명**
   |:-----|:-----|:-----|
   |`tenantId`|1 단계에서 구한 Microsoft 365 조직의 Id입니다. Azure AD 관리 센터의 **개요** 블레이드에서 조직에 대 한 tenantId를 가져올 수도 있습니다. 이는 조직을 식별 하는 데 사용 됩니다.|
   |`appId` |이는 1 단계에서 Azure AD에 만든 앱에 대 한 AAD 응용 프로그램 Id입니다. 스크립트에서 Microsoft 365 조직에 액세스 하려고 할 때 인증을 위해 Azure AD에서 사용 됩니다. | 
   |`appSecret`|이는 1 단계에서 Azure AD에 만든 앱에 대 한 AAD 응용 프로그램 비밀입니다. 인증에도 사용 됩니다.|
   |`jobId`|3 단계에서 만든 HR 커넥터의 작업 Id입니다. 이는 HR 커넥터를 사용 하 여 Microsoft 클라우드에 업로드 된 HR 데이터를 연결 하는 데 사용 됩니다.|
   |`csvFilePath`|2 단계에서 만든 CSV 파일에 대 한 로컬 컴퓨터 (스크립트를 실행 하는 데 사용 하는 사용자)의 파일 경로입니다. 파일 경로에 공백이 생기지 않도록 합니다. 그렇지 않으면 작은따옴표를 사용 합니다.|
   |||
   
   다음은 각 매개 변수에 대 한 실제 값을 사용 하는 HR connector 스크립트의 구문 예입니다.

   ```powershell
    .\HRConnector.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv'
    ```

   업로드가 성공 하면 스크립트에서 **업로드 성공** 메시지를 표시 합니다.

## <a name="step-5-monitor-the-hr-connector"></a>5 단계: HR 커넥터 모니터링

HR 커넥터를 만들고 스크립트를 실행 하 여 HR 데이터를 업로드 한 후에는 Microsoft 365 준수 센터에서 커넥터 및 업로드 상태를 볼 수 있습니다. 스크립트를 정기적으로 실행 하도록 예약 하는 경우 마지막으로 스크립트를 실행 한 후 현재 상태를 볼 수 있습니다.

1. [https://compliance.microsoft.com](https://compliance.microsoft.com) 으로 이동 하 여 왼쪽 탐색 창에서 **데이터 커넥터** 를 클릭 합니다.

2. **커넥터 탭을** 클릭 한 다음 HR 커넥터를 선택 하 여 커넥터에 대 한 속성 및 정보가 포함 된 플라이 아웃 페이지를 표시 합니다.

   ![속성 및 상태가 포함 된 HR 커넥터 플라이 아웃 페이지](../media/HRConnectorFlyout1.png)

3. **진행 중**에서 **로그 다운로드** 링크를 클릭 하 여 커넥터의 상태 로그를 열거나 저장 합니다. 이 로그는 스크립트가 실행 될 때마다 정보를 포함 하며 CSV 파일의 데이터를 Microsoft 클라우드에 업로드 합니다. 

   ![HR 커넥터 로그 파일은 업로드 된 CSV 파일의 번호 행을 표시 합니다.](../media/HRConnectorLogFile.png)

   **레코드 저장** 필드에는 CSV 파일에서 업로드 한 행의 수가 표시 됩니다. 예를 들어 CSV 파일에 4 개의 행이 포함 되어 있는 경우 스크립트에서 CSV 파일의 모든 행을 성공적으로 업로드 한 경우에는 **레코드에 저장** 된 필드의 값이 4가 됩니다.

4 단계에서 스크립트를 실행 하지 않은 경우 스크립트를 다운로드 하기 위한 링크가 **마지막 가져오기**아래에 표시 됩니다. 스크립트를 다운로드 한 다음 4 단계의 단계를 수행 하 여 실행할 수 있습니다.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>반드시 6 단계: 스크립트가 자동으로 실행 되도록 예약

조직의 최신 HR 데이터를 참가자 위험 관리 솔루션과 같은 도구로 사용할 수 있도록 하려면 하루에 한 번과 같이 반복 하 여 스크립트를 자동으로 실행 하도록 예약 하는 것이 좋습니다. 또한이 경우에는 동일한 일정에 따라 CSV 파일의 HR 데이터를 업데이트 해야 조직에서 탈퇴 하는 직원에 대 한 최신 정보가 포함 됩니다. HR 커넥터가 참가자 위험 관리 솔루션에서 사용할 수 있도록 최신 HR 데이터를 업로드 하는 것이 목표입니다.

Windows의 작업 스케줄러 응용 프로그램에서 매일 자동으로 스크립트를 실행할 수 있습니다.

1. 로컬 컴퓨터에서 Windows **시작** 단추를 클릭 한 다음 **작업 스케줄러**를 입력 합니다.

2. **작업 스케줄러** 앱을 클릭 하 여 엽니다.

3. **작업** 섹션에서 **작업 만들기**를 클릭 합니다.

4. **일반** 탭에서 예약 된 작업에 대 한 설명이 포함 된 이름을 입력 합니다. 예를 들어 **HR 커넥터 스크립트**를 예로 들 있습니다. 선택적 설명도 추가할 수 있습니다. 

5. **보안 옵션**에서 다음을 수행 합니다.

   a. 컴퓨터에 로그온 하거나 로그온 할 때 스크립트를 실행 하는 경우에만 실행할지를 결정 합니다.
   
   b. **가장 높은 권한으로 실행** 확인란이 선택 되어 있는지 확인 합니다.

6. **트리거** 탭을 선택 하 고 **새로 만들기**를 클릭 한 후 다음 작업을 수행 합니다.

   a. **설정**에서 **매일** 옵션을 선택한 다음 스크립트를 처음 실행할 날짜와 시간을 선택 합니다. 스크립트는 매일 같은 시간에 지정 됩니다.
   
   b. **고급 설정**에서 **사용** 확인란이 선택 되어 있는지 확인 합니다.
   
   c. **확인을**클릭 합니다.

7. **작업** 탭을 선택 하 고 **새로 만들기**를 클릭 한 후 다음 작업을 수행 합니다.

   ![HR 커넥터 스크립트에 대해 새로 예약 된 작업을 만들기 위한 작업 설정](../media/HRConnectorScheduleTask1.png)

   a. **작업** 드롭다운 목록에서 **프로그램 시작** 을 선택 했는지 확인 합니다.

   b. **프로그램/스크립트** 상자에서 **찾아보기를**클릭 하 고 다음 위치로 이동 하 여 경로를 상자에 표시 하도록 선택 `C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe`합니다.

   c. **인수 추가 (선택 사항)** 상자에 4 단계에서 실행 한 것과 동일한 스크립트 명령을 붙여 넣습니다. 예를 들어`.\HRConnector.ps1 -tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn"  -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -csvFilePath "C:\Users\contosoadmin\Desktop\Data\employee_termination_data.csv"`

   d. 시작 위치 **(선택 사항)** 상자에 4 단계에서 실행 한 스크립트의 폴더를 붙여 넣습니다. 예를 들면 `C:\Users\contosoadmin\Desktop\Scripts`와 같습니다.

   e. **확인** 을 클릭 하 여 새 작업에 대 한 설정을 저장 합니다.

8. **작업 만들기** 창에서 **확인** 을 클릭 하 여 예약 된 작업을 저장 합니다. 사용자 계정 자격 증명을 입력 하 라는 메시지가 표시 될 수 있습니다.

   새 작업이 작업 스케줄러 라이브러리에 표시 됩니다.

   ![새 작업이 작업 스케줄러 라이브러리에 표시 됨](../media/HRConnectorTaskSchedulerLibrary.png)

   스크립트를 마지막으로 실행 했을 때와 실행할 예약 된 다음 시간을 표시 합니다. 작업을 두 번 클릭 하 여 편집할 수 있습니다.

   또한 준수 센터의 해당 HR 커넥터에 대 한 플라이 아웃 페이지에서 스크립트를 마지막으로 실행 한 시간을 확인할 수 있습니다.
