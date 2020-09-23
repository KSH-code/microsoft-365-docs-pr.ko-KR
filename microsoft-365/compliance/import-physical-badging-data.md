---
title: 실제 배지 획득 데이터를 가져올 커넥터 설정
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
description: 관리자는 데이터 커넥터를 설정 하 여 조직의 실제 배지 획득 시스템에서 Microsoft 365로 데이터를 가져올 수 있습니다. 이를 통해 참가자 위험 관리 정책에서이 데이터를 사용 하 여 조직에 대 한 내부 위협을 나타낼 수 있는 특정 사용자의 실제 건물에 대 한 액세스를 감지 하는 데 도움을 받을 수 있습니다.
ms.openlocfilehash: 6d52879031c8801191b1a419f38a1167c1bb0688
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48204504"
---
# <a name="set-up-a-connector-to-import-physical-badging-data-preview"></a>실제 배지 획득 데이터를 가져올 커넥터 설정 (미리 보기)

Microsoft 365 준수 센터에서 데이터 커넥터를 설정 하 여 직원의 원시 물리적 액세스 이벤트 또는 조직의 배지 획득 시스템에서 생성 되는 실제 액세스 경보가 같은 실제 배지 획득 데이터를 가져올 수 있습니다. 실제 액세스 포인트의 예로는 건물이 나 서버 대화방 또는 데이터 센터에 대 한 항목을 들 수 있습니다. 실제 배지 획득 데이터는 Microsoft 365의 [참가자 위험 관리 솔루션](insider-risk-management.md) 에서 조직의 악의적인 활동 또는 데이터 절도 로부터 조직을 보호 하는 데 사용할 수 있습니다.

실제 배지 획득 커넥터 설정은 다음 작업으로 구성 됩니다.

- Azure Active Directory (Azure AD)에서 앱을 만들어 실제 배지 획득 데이터가 포함 된 JSON 페이로드를 허용 하는 API 끝점에 액세스 합니다.

- 실제 배지 획득 데이터 커넥터에 의해 정의 된 스키마를 사용 하 여 JSON 페이로드 만들기

- Microsoft 365 준수 센터에서 실제 배지 획득 데이터 커넥터 만들기

- 스크립트를 실행 하 여 실제 배지 획득 데이터를 API 끝점에 밀어 넣습니다.

- 필요한 경우 스크립트가 자동으로 실행 되도록 예약 하 여 현재 실제 배지 획득 데이터를 가져옵니다.

## <a name="before-you-set-up-the-connector"></a>커넥터를 설정 하기 전에

- 조직에서는 Office 365 가져오기 서비스가 조직의 데이터에 액세스 하도록 허용 하는 데 동의 해야 합니다. 이 요청에 동의 하려면 [이 페이지로](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent)이동 하 여 Microsoft 365 전역 관리자의 자격 증명으로 로그인 한 다음 요청을 수락 합니다. 3 단계에서 실제 배지 획득 커넥터를 성공적으로 만들기 전에이 단계를 완료 해야 합니다.

- 3 단계에서 실제 배지 획득 커넥터를 만드는 사용자에 게 Exchange Online의 사서함 가져오기 내보내기 역할이 할당 되어야 합니다. 기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다. Exchange Online의 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다. 또는 새 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당 한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "Exchange Online에서 역할 그룹 관리" 문서의 [역할 그룹 만들기](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) 또는 [역할 그룹 수정](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) 섹션을 참조 하세요.

- 조직의 실제 배지 획득 시스템에서 데이터를 검색 하거나 내보내는 방법 (일 단위)을 확인 하 고 2 단계에서 설명 하는 JSON 파일을 만드는 방법을 결정 해야 합니다. 4 단계에서 실행 하는 스크립트는 JSON 파일의 데이터를 API 끝점에 푸시합니다.

- 4 단계에서 실행 하는 예제 스크립트는 참가자 위험 관리 솔루션에서 사용할 수 있도록 JSON 파일의 실제 배지 획득 데이터를 커넥터 API에 푸시합니다. 이 샘플 스크립트는 Microsoft standard 지원 프로그램 또는 서비스에서 지원 되지 않습니다. 예제 스크립트는 어떤 종류의 보증도 없이 있는 그대로 제공 됩니다. 또한 Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다. 샘플 스크립트 및 설명서의 사용 또는 성능으로 인해 발생 하는 전체 위험은 사용자에 게 남아 있습니다. 어떠한 경우에도 Microsoft, 스크립트 작성자 또는 그외 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용할 수 없음으로 인해 발생하는 모든 손해(수익 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알았더라도 마찬가지입니다.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>1 단계: Azure Active Directory에 앱 만들기

첫 번째 단계는 Azure Active Directory (Azure AD)에서 새 앱을 만들고 등록 하는 것입니다. 이 앱은 3 단계에서 만든 실제 배지 획득 커넥터에 해당 합니다. 이 앱을 만들면 Azure AD에서 실제 배지 획득 데이터를 포함 하는 JSON 페이로드의 푸시 요청을 인증할 수 있습니다. 이 Azure AD 앱을 만드는 동안 다음 정보를 저장 해야 합니다. 이러한 값은 이후 단계에서 사용 됩니다.

- Azure AD 응용 프로그램 ID ( *앱 id* 또는 *클라이언트 ID*라고도 함)

- Azure AD 응용 프로그램 암호 ( *클라이언트 비밀이*라고도 함)

- 테 넌 트 Id ( *디렉터리 Id*라고도 함)

Azure AD에서 앱을 만드는 단계별 지침은 [Microsoft id 플랫폼을 사용 하 여 응용 프로그램 등록](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)을 참조 하세요.

## <a name="step-2-prepare-a-json-file-with-physical-badging-data"></a>2 단계: 실제 배지 획득 데이터를 사용 하 여 JSON 파일 준비

다음 단계는 직원의 실제 액세스 데이터에 대 한 정보가 포함 된 JSON 파일을 만드는 것입니다. 시작 하기 전에 섹션에서 설명한 것 처럼, 조직의 실제 배지 획득 시스템에서이 JSON 파일을 생성 하는 방법을 결정 해야 합니다.

JSON 파일은 커넥터에 필요한 스키마 정의를 준수 해야 합니다. 다음은 JSON 파일에 필요한 스키마 속성에 대 한 설명입니다.

|**속성**|**설명**|**Data type**|
|:-----------|:--------------|:------------|
|UserId|직원은 시스템 전체에 여러 디지털 id를 포함할 수 있습니다. 입력을 통해 원본 시스템에서 Azure AD ID를 이미 확인 해야 합니다. |UPN 또는 전자 메일 주소|
|AssetId|실제 자산 또는 실제 액세스 지점의 참조 ID입니다.| 영숫자 문자열|
|AssetName|실제 자산 또는 실제 액세스 포인트의 이름입니다.|영숫자 문자열|
|EventTime|액세스에 대 한 타임 스탬프입니다.|날짜 및 시간 (UTC 형식)|
|AccessStatus|값 `Success` 또는 `Failed`| 문자열|
|||

다음은 필요한 스키마를 준수 하는 JSON 파일의 예입니다.

```text
[
    {
        "UserId":"sarad@contoso.com"
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T01:57:49",
        "AccessStatus":"Failed",
    },
    {
        "UserId":"pilarp@contoso.com",        
        "AssetId":"Mid-Sec-7",
        "AssetName":"Main Building 1st Floor Mid Section",
        "EventTime":"2019-07-04T02:57:49",        
        "AccessStatus":"Success",
    }
]
```
3 단계에서 실제 배지 획득 커넥터를 만들 때 마법사에서 JSON 파일에 대 한 다음 스키마 정의를 다운로드할 수도 있습니다.

```text
{
    "title" : "Physical Badging Signals",
    "description" : "Access signals from physical badging systems",
    "DataType" : {
        "description" : "Identify what is the data type for input signal",
        "type" : "string",
    },
    "type" : "object",
    "properties": {
        "UserId" : {
            "description" : "Unique identifier AAD Id resolved by the source system",
            "type" : "string",
        },
        "AssetId": {
            "description" : "Unique ID of the physical asset/access point",
            "type" : "string",
        },
        "AssetName": {
            "description" : "friendly name of the physical asset/access point",
            "type" : "string",
        },
        "EventTime" : {
            "description" : "timestamp of access",
            "type" : "string",
        },
        "AccessStatus" : {
            "description" : "what was the status of access attempt - Success/Failed",
            "type" : "string",
        },
    }
    "required" : ["UserId", "AssetId", "EventTime" "AccessStatus"]
}
```

## <a name="step-3-create-the-physical-badging-connector"></a>3 단계: 실제 배지 획득 커넥터 만들기

다음 단계는 Microsoft 365 준수 센터에서 실제 배지 획득 커넥터를 만드는 것입니다. 4 단계에서 스크립트를 실행 하면 3 단계에서 만든 JSON 파일이 처리 된 후 1 단계에서 구성한 API 끝점에 푸시됩니다. 이 단계에서는 커넥터를 만들 때 생성 되는 JobId를 복사 해야 합니다. 스크립트를 실행할 때 JobId를 사용 합니다.

1. 로 이동한 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 후 왼쪽 탐색 창에서 **데이터 커넥터** 를 클릭 합니다.

2. **데이터 커넥터** 페이지의 **실제 배지 획득**에서 **보기**를 클릭 합니다.

3. **실제 배지 획득** 페이지에서 **커넥터 추가**를 클릭 합니다.

4. **인증 자격 증명** 페이지에서 다음을 수행한 후 **다음**을 클릭 합니다.
  
   1. 1 단계에서 만든 Azure 앱에 대 한 Azure AD 응용 프로그램 ID를 입력 하거나 붙여넣습니다.
  
   2. JSON 파일을 만들려면 참조용 샘플 스키마를 다운로드 하십시오.
  
   3. 실제 배지 획득 커넥터의 고유 이름을 입력 합니다.

5. **검토** 페이지에서 설정을 검토 하 고 **마침을** 클릭 하 여 커넥터를 만듭니다.

6. 커넥터를 만들었는지 확인 하는 상태 페이지가 표시 됩니다. 이 페이지에는 작업 ID도 포함 되어 있습니다. 이 페이지 또는 커넥터의 플라이 아웃 페이지에서 작업 ID를 복사할 수 있습니다. 스크립트를 실행할 때이 작업 ID가 필요 합니다.

   상태 페이지에도 스크립트에 대 한 링크가 포함 되어 있습니다. API 끝점에 JSON 파일을 게시 하는 방법을 알아보려면이 스크립트를 참조 하세요.

7. **완료**를 클릭합니다.

   새 커넥터가 **커넥터** 탭의 목록에 표시 됩니다.

8. 방금 만든 실제 배지 획득 커넥터를 클릭 하 여 커넥터에 대 한 속성 및 기타 정보를 포함 하는 플라이 아웃 페이지를 표시 합니다.

## <a name="step-4-run-the-script-to-post-your-json-file-containing-physical-badging-data"></a>4 단계: 스크립트를 실행 하 여 실제 배지 획득 데이터가 포함 된 JSON 파일 게시

실제 배지 획득 커넥터를 설정 하는 다음 단계는 2 단계에서 만든 JSON 파일의 실제 배지 획득 데이터를 1 단계에서 만든 API 끝점에 푸시하는 스크립트를 실행 하는 것입니다. 참조에 대 한 샘플 스크립트를 제공 하 고이를 사용 하거나 직접 스크립트를 만들어 API 끝점에 JSON 파일을 게시 하는 방법을 선택할 수 있습니다.

스크립트를 실행 한 후에는 배지 획득 데이터를 포함 하는 JSON 파일이 Microsoft 365 조직에 푸시되 며,이 파일은 사용자의 참가자 위험 관리 솔루션에서 액세스할 수 있습니다. 실제 배지 획득 데이터는 매일 게시 하는 것이 좋습니다. 이 작업은 실제 배지 획득 시스템에서 매일 JSON 파일을 생성 하는 프로세스를 자동화 하 고, 데이터를 푸시 하기 위해 스크립트를 예약 하 여 수행할 수 있습니다.

> [!NOTE]
> API에서 처리할 수 있는 JSON 파일의 최대 레코드 수는 5만 레코드입니다.

1. [이 GitHub 사이트로](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1) 이동 하 여 예제 스크립트에 액세스 합니다.

2. **Raw** 단추를 클릭 하 여 스크립트를 텍스트 보기로 표시 합니다.

3. 예제 스크립트의 모든 줄을 복사한 다음 텍스트 파일에 저장 합니다.

4. 필요한 경우 조직에 대 한 예제 스크립트를 수정 합니다.

5. 파일 이름 접미사. p s 1을 사용 하 여 텍스트 파일을 Windows PowerShell 스크립트 파일로 저장 합니다. 예를 PhysicalBadging.ps1 합니다.

6. 로컬 컴퓨터에서 명령 프롬프트를 열고 스크립트를 저장 한 디렉터리로 이동 합니다.

7. 다음 명령을 실행 하 여 JSON 파일의 실제 배지 획득 데이터를 Microsoft 클라우드로 밀어 넣습니다. 예를 들어:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId "<Tenant Id>" -appId "<Azure AD App Id>" -appSecret "<Azure AD App Secret>" -jobId "Job Id" -jsonFilePath "<records file path>"
   ```

   다음 표에서는이 스크립트와 함께 사용 하는 매개 변수와 해당 필수 값에 대해 설명 합니다. 이전 단계에서 얻은 정보는 이러한 매개 변수의 값에 사용 됩니다.

   | **매개 변수**|**설명**|
   |:-------------|:--------------|
   |tenantId | 1 단계에서 구한 Microsoft 365 조직의 Id입니다. Azure AD 관리 센터의 **개요** 블레이드에서 조직에 대 한 tenantId를 가져올 수도 있습니다. 이는 조직을 식별 하는 데 사용 됩니다. |
   |appId | 이는 1 단계에서 Azure AD에 만든 앱의 Azure AD 응용 프로그램 Id입니다. 스크립트에서 Microsoft 365 조직에 액세스 하려고 할 때 인증을 위해 Azure AD에서 사용 됩니다.                    |
   |appSecret | 이는 1 단계에서 Azure AD에 만든 앱에 대 한 Azure AD 응용 프로그램 비밀입니다. 인증에도 사용 됩니다.                                                        |
   |Id | 이는 3 단계에서 만든 실제 배지 획득 커넥터의 작업 Id입니다. 이는 실제 배지 획득 커넥터를 사용 하 여 Microsoft 클라우드에 푸시되는 실제 배지 획득 데이터를 연결 하는 데 사용 됩니다.              |
   |JsonFilePath | 2 단계에서 만든 JSON 파일에 대 한 로컬 컴퓨터 (스크립트를 실행 하는 데 사용 하는 사용자)의 파일 경로입니다. 이 파일은 3 단계에서 설명 하는 예제 스키마를 따라야 합니다.|
   |||

   다음은 각 매개 변수에 대 한 실제 값을 사용 하는 실제 배지 획득 커넥터 스크립트의 구문 예입니다.

   ```powershell
   .\PhysicalBadging.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json'
   ```

   업로드가 성공 하면 스크립트에서 **업로드 성공** 메시지를 표시 합니다.

   여러 JSON 파일이 있는 경우 각 파일에 대해 스크립트를 실행 해야 합니다.

> [!NOTE]
> 이전 스크립트를 실행 하는 것이 아닌 방법으로 실제 배지 획득 데이터를 API 끝점으로 푸시할 수도 있습니다. 예를 들어 다음은 Postman을 사용 하 여 데이터를 API 끝점에 푸시하는 예제입니다.

## <a name="step-5-monitor-the-physical-badging-connector"></a>5 단계: 실제 배지 획득 커넥터 모니터링

실제 배지 획득 커넥터를 만들고 실제 배지 획득 데이터를 밀어 넣는 후에는 Microsoft 365 준수 센터에서 커넥터 및 업로드 상태를 볼 수 있습니다. 스크립트를 정기적으로 실행 하도록 예약 하는 경우 마지막으로 스크립트를 실행 한 후 현재 상태를 볼 수 있습니다.

1. 으로 이동 하 여 [https://compliance.microsoft.com](https://compliance.microsoft.com/) 왼쪽 탐색 창에서 **데이터 커넥터** 를 클릭 합니다.

2. **커넥터** 탭을 클릭 한 다음 실제 배지 획득 커넥터를 선택 하 여 커넥터에 대 한 속성 및 정보가 포함 된 플라이 아웃 페이지를 표시 합니다.

   ![실제 배지 획득 커넥터에 대 한 상태 플라이 아웃 페이지](..\media\PhysicalBadgingStatusFlyout.png)

3. **마지막 가져오기**아래에서 **로그 다운로드** 링크를 클릭 하 여 커넥터의 상태 로그를 열거나 저장 합니다. 이 로그는 스크립트가 실행 될 때마다 정보를 포함 하며 CSV 파일의 데이터를 Microsoft 클라우드에 업로드 합니다.

   ![실제 배지 획득 커넥터 로그 파일은 업로드 된 JSON 파일의 번호 행을 표시 합니다.](..\media\PhysicalBadgingConnectorLogFile.png)

   **레코드 저장** 필드에는 CSV 파일에서 업로드 한 행의 수가 표시 됩니다. 예를 들어 CSV 파일에 행이 4 개 포함 되어 있으면 스크립트에서 CSV 파일의 모든 행을 성공적으로 업로드 한 경우 **레코드에 저장** 된 필드의 값은 4가 됩니다.

4 단계에서 스크립트를 실행 하지 않은 경우 스크립트를 다운로드 하기 위한 링크가 **마지막 가져오기**아래에 표시 됩니다. 스크립트를 다운로드 한 다음 4 단계의 단계를 수행 하 여 실행할 수 있습니다.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>반드시 6 단계: 스크립트가 자동으로 실행 되도록 예약

조직의 최신 물리적 배지 획득 데이터를 참가자 위험 관리 솔루션 같은 도구로 사용할 수 있도록 하려면 하루에 한 번과 같이 반복 하 여 스크립트를 자동으로 실행 하도록 예약 하는 것이 좋습니다. 또한 실제 배지 획득 데이터를 비슷한 (같지 않은 경우) 일정으로 JSON 파일에 업데이트 하 여 조직 내에서 탈퇴 하는 직원에 대 한 최신 정보를 포함 해야 합니다. 실제 배지 획득 커넥터를 참가자 위험 관리 솔루션에서 사용할 수 있도록 최신 실제 배지 획득 데이터를 업로드 하는 것이 목표입니다.

Windows의 작업 스케줄러 응용 프로그램에서 매일 자동으로 스크립트를 실행할 수 있습니다.

1. 로컬 컴퓨터에서 Windows **시작** 단추를 클릭 한 다음 **작업 스케줄러**를 입력 합니다.

2. **작업 스케줄러** 앱을 클릭 하 여 엽니다.

3. **작업** 섹션에서 **작업 만들기**를 클릭 합니다.

4. **일반** 탭에서 예약 된 작업에 대 한 설명이 포함 된 이름을 입력 합니다. 예를 들면 **실제 배지 획득 커넥터 스크립트**입니다. 선택적 설명도 추가할 수 있습니다.

5. **보안 옵션**에서 다음 작업을 수행 합니다.

   1. 컴퓨터에 로그온 하거나 로그온 할 때 스크립트를 실행 하는 경우에만 실행할지를 결정 합니다.

   2. **가장 높은 권한으로 실행** 확인란이 선택 되어 있는지 확인 합니다.

6. **트리거** 탭을 선택 하 고 **새로 만들기**를 클릭 한 후 다음 작업을 수행 합니다.

   1. **설정**에서 **매일** 옵션을 선택한 다음 스크립트를 처음 실행할 날짜와 시간을 선택 합니다. 스크립트는 매일 같은 시간에 지정 됩니다.

   2. **고급 설정**에서 **사용** 확인란이 선택 되어 있는지 확인 합니다.

   3. **확인을**클릭 합니다.

7. **작업** 탭을 선택 하 고 **새로 만들기**를 클릭 한 후 다음 작업을 수행 합니다.

   ![실제 배지 획득 커넥터 스크립트에 대해 새로 예약 된 작업을 만들기 위한 작업 설정](..\media\SchedulePhysicalBadgingScript1.png)

   1. **작업** 드롭다운 목록에서 **프로그램 시작** 을 선택 했는지 확인 합니다.

   2. **프로그램/스크립트** 상자에서 **찾아보기를**클릭 하 고 다음 위치로 이동 하 여 경로가 C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe 상자에 표시 되도록 선택 합니다.

   3. **인수 추가 (선택 사항)** 상자에 4 단계에서 실행 한 것과 동일한 스크립트 명령을 붙여 넣습니다. 예를 들어 .\PhysicalBadging.ps1-tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9"-appId "c12823b7-b55a-4989-faba-02de41bb97c3"-appSecret "MNubVGbcQDkGCnn"-jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458"-jsonFilePath "C:\Users\contosoadmin\Desktop\Data\physical_badging_data.csv"

   4. 시작 위치 **(선택 사항)** 상자에 4 단계에서 실행 한 스크립트의 폴더를 붙여 넣습니다. 예를 들어 C:\Users\contosoadmin\Desktop\Scripts.

   5. **확인** 을 클릭 하 여 새 작업에 대 한 설정을 저장 합니다.

8. **작업 만들기** 창에서 **확인** 을 클릭 하 여 예약 된 작업을 저장 합니다. 사용자 계정 자격 증명을 입력 하 라는 메시지가 표시 될 수 있습니다.

   새 작업이 작업 스케줄러 라이브러리에 표시 됩니다.

   ![새 작업이 작업 스케줄러 라이브러리에 표시 됨](..\media\SchedulePhysicalBadgingScript2.png)

스크립트를 마지막으로 실행 했을 때와 실행할 예약 된 다음 시간을 표시 합니다. 작업을 두 번 클릭 하 여 편집할 수 있습니다.

준수 센터의 해당 하는 실제 배지 획득 커넥터에 대 한 플라이 아웃 페이지에서 스크립트를 마지막으로 실행 한 시간을 확인할 수도 있습니다.
