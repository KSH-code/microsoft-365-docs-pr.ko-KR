---
title: 물리적 배지 데이터를 가져오는 커넥터 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: 관리자는 데이터 커넥터를 설정하여 조직의 물리적 배지 시스템에서 데이터 원본으로 데이터를 가져올 Microsoft 365. 이렇게 하면 내부자 위험 관리 정책에서 이 데이터를 사용하여 조직에 대한 내부 위협을 나타낼 수 있는 특정 사용자의 실제 건물 액세스를 검색할 수 있습니다.
ms.openlocfilehash: 042bd5f6089ff05d734ce6d2e159f5d3e3d104bd
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60668337"
---
# <a name="set-up-a-connector-to-import-physical-badging-data-preview"></a>물리적 배지 데이터를 가져오는 커넥터 설정(미리 보기)

직원의 원시 물리적 액세스 Microsoft 365 규정 준수 센터 또는 조직의 배지 시스템에 의해 생성된 물리적 액세스 알람과 같은 물리적 배지 데이터를 가져오기 위해 데이터 커넥터를 설정할 수 있습니다. 실제 액세스 지점의 예로는 건물에 대한 항목이나 서버 방 또는 데이터 센터에 대한 항목이 있습니다. 조직의 내부자 위험 관리 솔루션에서 물리적 [배지](insider-risk-management.md) Microsoft 365 사용하여 조직 내부의 악의적인 활동이나 데이터 도용으로부터 조직을 보호할 수 있습니다.

실제 배지 커넥터를 설정하는 작업은 다음과 같은 작업으로 구성됩니다.

- Azure AD(Azure Active Directory)에서 앱을 만들어 실제 배지 데이터가 포함된 JSON 페이로드를 허용하는 API 끝점에 액세스합니다.

- 물리적 배지 데이터 커넥터로 정의된 Schema를 사용하여 JSON 페이로드 만들기

- 배지 데이터 커넥터를 만드는 Microsoft 365 규정 준수 센터.

- 실제 배지 데이터를 API 끝점에 푸시하기 위해 스크립트를 실행합니다.

- 선택적으로, 현재 물리적 배지 데이터를 가져오기 위해 스크립트가 자동으로 실행될 수 있습니다.

## <a name="before-you-set-up-the-connector"></a>커넥터를 설정하기 전에

- 3단계에서 실제 배지 커넥터를 만드는 사용자에게 사서함 가져오기 내보내기 역할이 할당되어야 Exchange Online. 기본적으로이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다. 사서함 가져오기 내보내기 역할을 조직의 조직 관리 역할 그룹에 추가할 수 Exchange Online. 또는 새 역할 그룹을 만들고 사서함 가져오기 내보내기 역할을 할당한 다음 해당 사용자를 구성원으로 추가할 수 있습니다. 자세한 내용은 "역할 [](/Exchange/permissions-exo/role-groups#create-role-groups) 그룹에서 [](/Exchange/permissions-exo/role-groups#modify-role-groups) 역할 그룹 관리" 문서의 역할 그룹 만들기 또는 역할 그룹 수정 섹션을 Exchange Online.

- 조직의 물리적 배지 시스템에서 데이터를 검색하거나 내보내는 방법을 결정하고(매일) 2단계에 설명된 JSON 파일을 만들어야 합니다. 4단계에서 실행한 스크립트는 JSON 파일의 데이터를 API 끝점으로 푸시합니다.

- 4단계에서 실행한 샘플 스크립트는 내부자 위험 관리 솔루션에서 사용할 수 있도록 JSON 파일의 실제 배지 데이터를 커넥터 API로 푸시합니다. 이 샘플 스크립트는 Microsoft 표준 지원 프로그램 또는 서비스에서 지원되지 않습니다. 샘플 스크립트는 어떤 종류의 보증도 없이 그대로 제공됩니다. 또한 Microsoft는 묵시적인 모든 보증(상품성 또는 특정 목적에의 적합성에 대한 묵시적인 보증을 포함하되 이에 제한되지 않음)을 부인합니다. 샘플 스크립트 및 문서의 사용 또는 수행으로 인해 발생하는 모든 위험은 사용자의 책임입니다. 어떠한 경우에도 Microsoft, 스크립트 작성자 또는 그외 스크립트의 작성, 생산 또는 제공과 관련된 사람은 누구나 샘플 스크립트 또는 문서의 사용 또는 사용할 수 없음으로 인해 발생하는 모든 손해(수익 손실, 비즈니스 중단, 비즈니스 정보 손실 또는 기타 금전상의 손실을 포함하되 이에 제한되지 않음)에 대해 책임지지 않습니다. 이는 Microsoft가 이러한 손해가 발생할 가능성에 대해 알았더라도 마찬가지입니다.

- 이 커넥터는 미국 GCC 클라우드의 Microsoft 365 환경에서 사용할 수 있습니다. 타사 응용 프로그램 및 서비스는 Microsoft 365 인프라 외부에 있는 타사 시스템에서 조직의 고객 데이터를 저장, 전송 및 처리해야 할 수 있으므로 Microsoft 365 및 데이터 보호 약정의 적용을 Microsoft 365 수 있습니다. Microsoft는 타사 응용 프로그램에 연결하는 데 이 제품을 사용하는 것은 해당 타사 응용 프로그램이 FEDRAMP 규격임을 암시하는 표현을 사용하지 않습니다.

## <a name="step-1-create-an-app-in-azure-active-directory"></a>1단계: 앱에서 앱 Azure Active Directory

첫 번째 단계는 Azure AD(Azure AD)에서 새 Azure Active Directory 등록하는 것입니다. 앱은 3단계에서 만든 실제 배지 커넥터에 해당합니다. 이 앱을 만들면 Azure AD에서 실제 배지 데이터가 포함된 JSON 페이로드에 대한 푸시 요청을 인증할 수 있습니다. 이 Azure AD 앱을 만들 때 다음 정보를 저장해야 합니다. 이러한 값은 이후 단계에서 사용됩니다.

- Azure AD 응용 프로그램 ID(앱 ID 또는 *클라이언트 ID라고도 합니다.* 

- Azure AD 응용 프로그램 비밀(클라이언트 *비밀이라고도 합니다.*

- 테넌트 ID(디렉터리 *ID라고도 합니다.*

Azure AD에서 앱을 만드는 단계별 지침은 응용 프로그램 등록을 [Microsoft ID 플랫폼.](/azure/active-directory/develop/quickstart-register-app)

## <a name="step-2-prepare-a-json-file-with-physical-badging-data"></a>2단계: 실제 배지 데이터를 사용하여 JSON 파일 준비

다음 단계는 직원의 실제 액세스 데이터에 대한 정보가 포함된 JSON 파일을 만드는 것입니다. 시작하기 전에 섹션에서 설명한 것 처럼 조직의 물리적 배지 시스템에서 이 JSON 파일을 생성하는 방법을 결정해야 합니다.

JSON 파일은 커넥터에 필요한 Schema 정의를 준수해야 합니다. JSON 파일에 필요한 Schema 속성에 대한 설명은 다음과 같습니다.

|속성|설명|데이터 형식|
|---|---|---|
|UserId|직원은 시스템 전체에서 여러 디지털 ID를 사용할 수 있습니다. 입력에는 원본 시스템에서 Azure AD ID가 이미 확인되어 있습니다.|UPN 또는 전자 메일 주소|
|AssetId|실제 자산 또는 물리적 액세스 지점의 참조 ID입니다.|영문 문자열|
|AssetName|실제 자산 또는 물리적 액세스 지점의 이름입니다.|영문 문자열|
|EventTime|액세스의 타임스탬프입니다.|날짜 및 시간(UTC 형식)|
|AccessStatus|또는 `Success``Failed`|문자열|
|||

다음은 필요한 Schema를 준수하는 JSON 파일의 예입니다.

```json
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

3단계에서 실제 배지 커넥터를 만들 때 마법사에서 JSON 파일에 대한 다음의 Schema 정의를 다운로드할 수 있습니다.

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

## <a name="step-3-create-the-physical-badging-connector"></a>3단계: 물리적 배지 커넥터 만들기

다음 단계는 웹 에지에서 실제 배지 커넥터를 Microsoft 365 규정 준수 센터. 4단계에서 스크립트를 실행하면 3단계에서 만든 JSON 파일이 처리 및 1단계에서 구성한 API 끝점으로 푸시됩니다. 이 단계에서는 커넥터를 만들 때 생성된 JobId를 복사해야 합니다. 스크립트를 실행할 때 JobId를 사용하게 됩니다.

1. 으로 이동한 다음 왼쪽 <https://compliance.microsoft.com> **네비게이트에서 데이터** 커넥터를 클릭합니다.

2. 실제 **배지** 아래의 데이터 커넥터 페이지에서 **보기를** **클릭합니다.**

3. 물리적 **배지 페이지에서** 커넥터 **추가를 클릭합니다.**

4. 인증 **자격 증명 페이지에서** 다음을 클릭하고 다음을 **클릭합니다.**

   1. 1단계에서 만든 Azure 앱의 Azure AD 응용 프로그램 ID를 입력하거나 붙여넣습니다.

   2. 참조에 대한 예제 Schema를 다운로드하여 JSON 파일을 만들 수 있습니다.

   3. 실제 배지 커넥터의 고유한 이름을 입력합니다.

5. 검토 **페이지에서** 설정을 검토한 다음 **마친을** 클릭하여 커넥터를 만드십시오.

6. 커넥터가 만들어졌다는 확인 상태 페이지가 표시됩니다. 이 페이지에는 작업 ID도 포함되어 있습니다. 이 페이지 또는 커넥터의 플라이아웃 페이지에서 작업 ID를 복사할 수 있습니다. 스크립트를 실행하는 경우 이 작업 ID가 필요합니다.

   상태 페이지에는 스크립트에 대한 링크도 포함되어 있습니다. 이 스크립트를 참조하여 JSON 파일을 API 끝점에 게시하는 방법을 이해합니다.

7. **완료** 를 클릭합니다.

   새 커넥터가 커넥터 탭의 목록에 **표시됩니다.**

8. 방금 만든 실제 배지 커넥터를 클릭하여 커넥터에 대한 속성 및 기타 정보가 포함된 플라이아웃 페이지를 표시합니다.

## <a name="step-4-run-the-script-to-post-your-json-file-containing-physical-badging-data"></a>4단계: 실제 배지 데이터가 포함된 JSON 파일을 POST하는 스크립트 실행

실제 배지 커넥터를 설정하는 다음 단계는 1단계에서 만든 API 끝점에 JSON 파일(2단계에서 만든)의 실제 배지 데이터를 푸시하는 스크립트를 실행하는 것입니다. 참조를 위한 샘플 스크립트를 제공하고 이를 사용하거나 JSON 파일을 API 끝점에 게시하기 위한 자체 스크립트를 만들 수 있습니다.

스크립트를 실행하면 실제 배지 데이터가 포함된 JSON 파일이 내부자 위험 관리 솔루션에서 액세스할 수 있는 Microsoft 365 조직으로 푸시됩니다. 물리적 배지 데이터를 매일 게시하는 것이 좋습니다. 이 작업을 위해 물리적 배지 시스템에서 매일 JSON 파일을 생성하는 프로세스를 자동화한 다음 스크립트를 실행하여 데이터를 푸시하도록 할 수 있습니다.

> [!NOTE]
> API에서 처리될 수 있는 JSON 파일의 최대 레코드 수는 50,000개 레코드입니다.

1. 이 [GitHub 사이트로 이동하여](https://github.com/microsoft/m365-hrconnector-sample-scripts/blob/master/upload_termination_records.ps1) 샘플 스크립트에 액세스합니다.

2. 원시 **단추를** 클릭하여 텍스트 보기에 스크립트를 표시합니다.

3. 샘플 스크립트의 모든 줄을 복사한 다음 텍스트 파일에 저장합니다.

4. 필요한 경우 조직의 샘플 스크립트를 수정합니다.

5. 파일 이름 접미사로 Windows PowerShell 스크립트 파일로 텍스트 파일을 .ps1. 예를 들어 PhysicalBadging.ps1.

6. 로컬 컴퓨터에서 명령 프롬프트를 열고 스크립트를 저장한 디렉터리로 이동하십시오.

7. 다음 명령을 실행하여 JSON 파일의 실제 배지 데이터를 Microsoft 클라우드로 푸시합니다. 예를 들어:

   ```powershell
   .\PhysicalBadging.ps1 -tenantId "<Tenant Id>" -appId "<Azure AD App Id>" -appSecret "<Azure AD App Secret>" -jobId "Job Id" -jsonFilePath "<records file path>"
   ```

   다음 표에서는 이 스크립트와 함께 사용할 매개 변수와 필요한 값에 대해 설명합니다. 이전 단계에서 얻은 정보는 이러한 매개 변수의 값에 사용됩니다.

   |매개 변수|설명|
   |---|---|
   |tenantId|1단계에서 획득한 Microsoft 365 조직의 ID입니다. Azure AD 관리 센터의 개요 블레이드에서  조직의 tenantId를 얻을 수도 있습니다. 이는 조직을 식별하는 데 사용됩니다.|
   |appId|1단계에서 Azure AD에서 만든 앱의 Azure AD 응용 프로그램 ID입니다. 스크립트가 사용자 조직에 액세스하려고 할 때 Azure AD에서 Microsoft 365 사용됩니다.|
   |appSecret|1단계에서 Azure AD에서 만든 앱의 Azure AD 응용 프로그램 비밀입니다. 이는 인증에도 사용됩니다.|
   |jobId|3단계에서 만든 실제 배지 커넥터의 작업 ID입니다. 이는 Microsoft 클라우드로 푸시되는 물리적 배지 데이터를 실제 배지 커넥터와 연결하기 위해 사용됩니다.|
   |JsonFilePath|2단계에서 만든 JSON 파일의 로컬 컴퓨터(스크립트를 실행하기 위해 사용하는 파일 경로)입니다. 이 파일은 3단계에 설명된 예제 schema를 따라야 합니다.|
   |||

   다음은 각 매개 변수에 대해 실제 값을 사용하는 실제 배지 커넥터 스크립트 구문의 예입니다.

   ```powershell
   .\PhysicalBadging.ps1 -tenantId d5723623-11cf-4e2e-b5a5-01d1506273g9 -appId 29ee526e-f9a7-4e98-a682-67f41bfd643e -appSecret MNubVGbcQDkGCnn -jobId b8be4a7d-e338-43eb-a69e-c513cd458eba -csvFilePath 'C:\Users\contosoadmin\Desktop\Data\physical_badging_data.json'
   ```

   업로드가 성공하면 스크립트에 성공한 업로드 **표시됩니다.**

   JSON 파일이 여러 개 있는 경우 각 파일에 대해 스크립트를 실행해야 합니다.

> [!NOTE]
> 또한 이전 스크립트를 실행하는 것이 아니라 다른 메서드를 사용하여 실제 배지 데이터를 API 끝점에 푸시할 수도 있습니다. 예를 들어 Postman을 사용하여 데이터를 API 끝점에 푸시하기 위한 샘플은 다음과 같습니다.

## <a name="step-5-monitor-the-physical-badging-connector"></a>5단계: 실제 배지 커넥터 모니터링

실제 배지 커넥터를 만들고 실제 배지 데이터를 푸시한 후 커넥터를 보고 해당 커넥터의 업로드 상태를 Microsoft 365 규정 준수 센터. 스크립트가 정기적으로 자동으로 실행될 수 있는 경우 스크립트가 마지막으로 실행된 후 현재 상태를 볼 수도 있습니다.

1. 으로 <https://compliance.microsoft.com> 이동하여 왼쪽 **nav에서 데이터** 커넥터를 클릭합니다.

2. 커넥터 **탭을** 클릭한 다음 실제 배지 커넥터를 선택하여 플라이아웃 페이지를 표시합니다. 이 페이지에는 커넥터에 대한 속성과 정보가 포함되어 있습니다.

   ![실제 배지 커넥터의 상태 플라이아웃 페이지입니다.](..\media\PhysicalBadgingStatusFlyout.png)

3. 마지막 **가져오기 아래에서** 로그 다운로드 링크를 클릭하여 커넥터의 상태 로그를 열거나 저장합니다.  이 로그에는 스크립트를 실행하고 CSV 파일의 데이터를 Microsoft 클라우드에 업로드할 때마다 대한 정보가 포함되어 있습니다.

   ![실제 배지 커넥터 로그 파일에는 업로드된 JSON 파일의 숫자 행이 표시됩니다.](..\media\PhysicalBadgingConnectorLogFile.png)

   **RecordsSaved** 필드는 업로드한 CSV 파일의 행 수를 나타냅니다. 예를 들어 CSV 파일에 4개의 행이 포함되어 있는 경우 **스크립트가 CSV** 파일의 모든 행을 업로드한 경우 RecordsSaved 필드의 값은 4입니다.

4단계에서 스크립트를 실행하지 않은 경우 마지막 가져오기 아래에 스크립트를 다운로드하는 **링크가 표시됩니다.** 스크립트를 다운로드한 다음 4단계의 단계에 따라 스크립트를 실행할 수 있습니다.

## <a name="optional-step-6-schedule-the-script-to-run-automatically"></a>(선택 사항) 6단계: 스크립트가 자동으로 실행 예약

조직의 최신 물리적 배지 데이터를 내부자 위험 관리 솔루션과 같은 도구에서 사용할 수 있도록 1일 1회와 같이 스크립트가 자동으로 실행될 수 있도록 예약하는 것이 좋습니다. 또한 물리적 배지 데이터를 조직을 떠나는 직원에 대한 최신 정보를 포함하기 위해 유사한 일정(같지 않은 경우)의 JSON 파일로 업데이트해야 합니다. 목표는 내부자 위험 관리 솔루션에서 실제 배지 커넥터를 사용할 수 있도록 가장 최근의 물리적 배지 데이터를 업로드하는 것입니다.

작업 스케줄러 앱을 사용자 Windows 자동으로 스크립트를 실행할 수 있습니다.

1. 로컬 컴퓨터에서 시작 Windows **클릭한** 다음 작업 스케줄러 **를 입력합니다.**

2. 작업 **스케줄러 앱을 클릭하여** 열립니다.

3. 작업 **섹션에서** 작업 **만들기 를 클릭합니다.**

4. 일반 **탭에서** 예약된 작업에 대한 설명적인 이름을 입력합니다. 예를 들어 실제 **배지 커넥터 Script입니다.** 선택적 설명을 추가할 수도 있습니다.

5. 보안 **옵션에서** 다음을 합니다.

   1. 컴퓨터에 로그온할 때만 스크립트를 실행할지 로그온할 때 스크립트를 실행할지 여부를 결정하십시오.

   2. 가장 높은 **권한으로** 실행 확인란이 선택되어 있는지 확인 합니다.

6. 트리거 **탭을** 선택하고 새로 **고치기를** 클릭한 후 다음을 실행합니다.

   1. 이 **설정** 에서 일별 옵션을 선택한 다음 처음으로 스크립트를 실행할 날짜와 시간을 선택합니다.  스크립트는 매일 같은 지정된 시간으로 실행됩니다.

   2. 고급 **설정에서** 사용 **확인란이** 선택되어 있는지 확인합니다.

   3. 확인을 **클릭합니다.**

7. 작업 **탭을** 선택하고 새로 **고치기를** 클릭한 후 다음을 수행하십시오.

   ![실제 배지 커넥터 스크립트에 대해 예약된 새 작업을 만들기 위한 작업 설정](..\media\SchedulePhysicalBadgingScript1.png)

   1. 작업 **드롭다운** 목록에서 프로그램 시작이 선택되어 **있는지** 확인 합니다.

   2. **프로그램/스크립트** 상자에서 찾아보기를 클릭하고 다음 위치로 이동하여 경로가 상자에 표시될 수 있도록 C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe. 

   3. 인수 **추가(선택 사항)** 상자에 4단계에서 실행한 동일한 스크립트 명령을 붙여 넣습니다. 예를 들면 다음과 같습니다. .\PhysicalBadging.ps1-tenantId "d5723623-11cf-4e2e-b5a5-01d1506273g9" -appId "c12823b7-b55a-4989-faba-02de41bb97c3" -appSecret "MNubVGbcQDkGCnn" -jobId "e081f4f4-3831-48d6-7bb3-fcfab1581458" -jsonFilePath "C:\Users\contosoadmin\Desktop\Data\physical_badging_data.csv"

   4. 시작 **위치(선택 사항)** 상자에 4단계에서 실행한 스크립트의 폴더 위치를 붙여 넣습니다. 예를 들어 C:\Users\contosoadmin\Desktop\Scripts와 같습니다.

   5. **확인을** 클릭하여 새 작업의 설정을 저장합니다.

8. 작업 **만들기 창에서** **확인을** 클릭하여 예약된 작업을 저장합니다. 사용자 계정 자격 증명을 입력하라는 메시지가 표시될 수 있습니다.

   새 작업이 작업 스케줄러 라이브러리에 표시됩니다.

   ![새 작업이 작업 스케줄러 라이브러리에 표시됩니다.](..\media\SchedulePhysicalBadgingScript2.png)

스크립트가 마지막으로 실행된 시간 및 다음에 실행 예약이 표시됩니다. 작업을 두 번 클릭하여 편집할 수 있습니다.

또한 준수 센터에서 해당 물리적 배지 커넥터의 플라이아웃 페이지에서 스크립트가 마지막으로 실행된 시간을 확인할 수도 있습니다.
