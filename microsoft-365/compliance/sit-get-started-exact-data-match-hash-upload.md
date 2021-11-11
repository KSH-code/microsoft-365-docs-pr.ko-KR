---
title: 정확한 데이터 일치 중요한 정보 유형에 대한 중요한 정보 원본 테이블 해시 및 업로드
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 정확한 데이터가 중요한 정보 유형과 일치하는 중요한 정보 원본 테이블을 해시하고 업로드합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 85a65bc0d9d68a4a148fbc820985b6f40b6f6792
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914897"
---
# <a name="hash-and-upload-the-sensitive-information-source-table-for-exact-data-match-sensitive-information-types"></a>정확한 데이터 일치 중요한 정보 유형에 대한 중요한 정보 원본 테이블 해시 및 업로드

이 문서에서는 중요한 정보 원본 테이블을 해시하고 업로드하는 방법을 보여줍니다.

## <a name="hash-and-upload-the-sensitive-information-source-table"></a>중요한 정보 원본 테이블 해시 및 업로드

이 단계에서는 다음을 진행합니다.

1. 사용자 지정 보안 그룹 및 사용자 계정 설정
2. EDM 업로드 에이전트 도구 설정
3. EDM 업로드 에이전트 도구를 사용하여 솔트 값, 중요한 정보 원본 테이블을 사용하여 해시한 다음 업로드합니다.

해시 및 업로드는 한 대의 컴퓨터를 사용하여 수행하거나 보안 강화를 위해 업로드 단계에서 해싱 단계를 분리할 수 있습니다.

한 대의 컴퓨터에서 해시하고 업로드하려면 Microsoft 365 테넌트에 직접 연결할 수 있는 컴퓨터에서 수행해야 합니다. 이렇게 하려면 해시를 위해 해당 컴퓨터에 명확한 텍스트 중요한 정보 원본 테이블 파일이 필요합니다.

직접 액세스 컴퓨터에 명확한 텍스트 중요한 정보 원본 테이블 파일을 노출하지 않을 경우 안전한 위치에 있는 컴퓨터에서 해시한 다음 업로드를 위해 Microsoft 365 테넌트에 직접 연결할 수 있는 컴퓨터에 해시 파일과 솔트 파일을 복사할 수 있습니다. 분리된 해시 및 업로드 시나리오에서는 두 컴퓨터 모두에 EDMUploadAgent가 필요합니다.

> [!IMPORTANT]
> 정확한 데이터 일치 schema 및 중요한 정보 유형 마법사를 사용하여 스마마 파일을 만든 경우 아직 이 절차에 대한 스마마를 다운로드하지 않은 경우 이 절차에 대한 스마마를 다운로드해야 합니다.  [EDM schema](sit-get-started-exact-data-match-create-schema.md#export-of-the-edm-schema-file-in-xml-format)파일 내보내기(XML 형식)를 참조합니다.

> [!NOTE]
> 조직에서 테넌트 [](customer-key-overview.md)Microsoft 365 사용자에 대한 고객 키를 설정한 경우 정확한 데이터 일치는 암호화 기능을 자동으로 사용합니다. 상업용 클라우드의 E5 라이선스 테넌트에서만 사용할 수 있습니다.

### <a name="best-practices"></a>모범 사례

프로세스에서 문제를 보다 쉽게 격리할 수 있도록 중요한 데이터를 해시하고 업로드하는 프로세스를 분리합니다.
 
프로덕션이 완료된 후 대부분의 경우 두 단계를 별도로 유지하십시오. 격리된 컴퓨터에서 해시 프로세스를 수행한 다음 인터넷 연결 컴퓨터에 업로드할 파일을 전송하면 인터넷에 연결하여 손상될 수 있는 컴퓨터에서 실제 데이터를 명확한 텍스트 형태로 사용할 수 없습니다.

### <a name="ensure-your-sensitive-data-table-doesnt-have-formatting-issues"></a>중요한 데이터 테이블에 서식 문제가 없는지 확인 

중요한 데이터를 해시하고 업로드하기 전에 검색을 통해 콘텐츠 구문 분석에 문제가 발생할 수 있는 특수 문자의 존재 여부를 검사합니다. 다음 구문과 함께 EDM 업로드 에이전트를 사용하여 테이블이 EDM에 적합한 형식이 맞는지 확인할 수 있습니다.

```powershell
EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file] 
```

도구에서 열 수가 불일치한 것으로 표시되면 표의 값 내에 콤보 문자나 따옴표 문자가 존재하여 열을 따옴표로 하여 혼동을 하게 될 수 있습니다. 전체 값을 둘러싸지 않는 한 단일 따옴표와 따옴표를 사용하면 도구에서 개별 열이 시작되거나 끝나는 위치를 잘못 알 수 있습니다. 

**전체값을 둘러싼** 따옴표 문자나 따옴표 문자를 찾으면 그대로 둘 수 있습니다.

값 내에서 작은 따옴표나 콤보 문자가 발견되는 **경우:** 예를 들어 사람의 이름 Tom O'Neil 또는 아포스트로피 문자로 시작하는 구/시의 S-Quotenhage를 찾으면 중요한 정보 표를 생성하는 데 사용되는 데이터 내보내기 프로세스를 수정하여 이러한 열을 작은 따옴표로 둘러싸야 합니다.

**값 내에서 작은** 따옴표 문자가 발견되는 경우 이러한 문제에 덜 받기 까다로운 표에 Tab으로분석된 형식을 사용하는 것이 좋습니다.

### <a name="prerequisites"></a>필수 구성 요소

- **EDM\_DataUploaders** 보안 그룹에 추가될 Microsoft 365용 회사 또는 학교 계정
- .NET Windows 10 4.6.Windows Server 2016 컴퓨터 또는 컴퓨터 <!--4.7.2 un comment this around 9/29-->EDMUploadAgent 실행
- 다음에 대한 업로드 컴퓨터의 디렉토리 :
  - [EDM 업로드 에이전트](#links-to-edm-upload-agent-by-subscription-type)
  - 예제에 설명된 .csv .tsv 또는 파이프(|) 형식의 PatientRecords.csv파일
  - 이 절차에서 만든 출력 해시 및 솔트 파일
  - **edm.xml** 파일의 데이터 저장소 이름(이 예에서는 `PatientRecords`)

#### <a name="set-up-the-security-group-and-user-account"></a>보안 그룹 및 사용자 계정 설정

1. 전역 관리자로서 [구독에 대한 적절한 링크](sit-get-started-exact-data-match-based-sits-overview.md#portal-links-for-your-subscription)를 사용하여 관리 센터로 이동하고 **EDM\_ DataUploaders** 라는 [보안 그룹을 만듭니다](/office365/admin/email/create-edit-or-delete-a-security-group).

2. 한 명 이상의 사용자를 **EDM\_DataUploaders** 보안 그룹에 추가합니다. (이러한 사용자가 중요한 정보 데이터베이스를 관리합니다.)

### <a name="hash-and-upload-from-one-computer"></a>한 대의 컴퓨터에서 해시 및 업로드

이 컴퓨터는 Microsoft 365 테넌트에 직접 액세스할 수 있어야 합니다.

> [!NOTE]
> 이 절차를 시작하기 전에 본인이 **EDM\_DataUploaders** 보안 그룹의 구성원인지 확인하세요.

> [!TIP] 
>선택적으로 중요한 정보 원본 테이블 파일에 대해 유효성 검사를 실행하여 업로드하기 전에 오류를 확인할 수 있습니다.
>
> `EdmUploadAgent.exe /ValidateData /DataFile [data file] /Schema [schema file]`
>
> 지원되는 모든 매개 변수에 대한 자세한 EdmUploadAgent.exe 실행
>
> `EdmUploadAgent.exe /?`

#### <a name="links-to-edm-upload-agent-by-subscription-type"></a>구독 유형별 EDM 업로드 에이전트에 대한 링크

- [상업용 + GCC](https://go.microsoft.com/fwlink/?linkid=2088639) - 대부분의 상업용 고객이 사용
- [GCC-High](https://go.microsoft.com/fwlink/?linkid=2137521) - 특히 높은 보안 정부 클라우드 구독자용
- [DoD](https://go.microsoft.com/fwlink/?linkid=2137807) - 특히 미국 국방부 클라우드 고객용

1. EDMUploadAgent에 대한 작업 디렉터리를 만듭니다. 예를 들어, **C:\EDM\Data**. 여기에 **PatientRecords.csv** 파일을 배치하세요.

2. 구독에 적합한 [EDM 업로드 에이전트](#links-to-edm-upload-agent-by-subscription-type)를 1단계에서 만든 디렉토리에 다운로드하여 설치합니다.

   > [!NOTE]
   > 위 링크의 EDMUploadAgent는 해시된 데이터에 솔트 값을 자동으로 추가하도록 업데이트되었습니다. 또는 자신의 솔트 값을 입력할 수 있습니다. 이 버전을 사용한 후에는 이전 버전의 EDMUploadAgent를 사용할 수 없습니다.
   >
   > EDMUploadAgent를 사용하여 하루에 두 번만 지정된 데이터 저장소에 데이터를 업로드할 수 있습니다.

3. EDM 업로드 에이전트에 권한을 설정하고 관리자 권한으로 명령 프롬프트 창을 열고 **C:\EDM\Data** 디렉터리로 전환한 후 다음 명령을 실행합니다.

   `EdmUploadAgent.exe /Authorize`

> [!IMPORTANT]
> **EdmUploadAgent가 설치된 폴더에서 EdmUploadAgent를** 실행하고 데이터 파일의 전체 경로를 지정해야 합니다. 

4. EDM_DataUploaders 보안 그룹에 추가된 Microsoft 365용 회사 또는 학교 계정으로 로그인합니다. 테넌트 정보는 연결을 위해 사용자 계정에서 추출됩니다.

   선택 사항: 정확한 데이터 일치chema 및 중요한 정보 유형 마법사를 사용하여  스마마를 만든 경우 아직 이 절차에서 사용할 수 있도록 다운로드해야 합니다. 명령 프롬프트 창에서 이 명령을 실행합니다.

   ```dos
   EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>
   ```

5. 중요한 데이터를 해시하고 업로드하려면 명령 프롬프트 창에서 다음 명령을 실행하세요.

   ```dos
   EdmUploadAgent.exe /UploadData /DataStoreName [DS Name] /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] /ColumnSeparator ["{Tab}"|"|"] /AllowedBadLinesPercentage [value]
   ```
   > [!NOTE]
> 중요한 데이터 파일의 기본 형식은 콤보로 구분된 값입니다. /ColumnSeparator 매개 변수를 사용하여 "{Tab}" 옵션을 지정하여 탭으로 구분된 파일을 지정하거나 "|" 옵션을 지정하여 파이프로 구분된 파일을 지정할 수 있습니다.

   예: **EdmUploadAgent.exe /UploadData /DataStoreName PatientRecords /DataFile C:\Edm\Hash\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml /AllowedBadLinesPercentage 5**

중요한 정보 테이블에 형식이 잘못 지정되어 있지만 잘못된 행을 아우르는 동안 나머지 데이터를 가져오고자 하는 경우 명령에서 */AllowedBadLinesPercentage* 매개 변수를 사용할 수 있습니다. 위의 예제에서는 5% 임계값을 지정합니다. 즉, 행의 최대 5%가 유효하지 않은 경우에도 도구가 중요한 정보 테이블을 해시하고 업로드합니다. 

이 명령은 보안을 강화하기 위해 임의로 생성된 솔트 값을 해시에 자동으로 추가합니다. 선택에 따라, 고유한 솔트 값을 사용하려면 **/Salt <saltvalue>** 를 명령에 추가하세요. 이 값은 길이가 64자여야 하며 a-z 문자와 0-9만 포함할 수 있습니다.

6. 다음 명령을 실행하여 업로드 상태를 확인하세요.

   ```dos
   EdmUploadAgent.exe /GetSession /DataStoreName \<DataStoreName\>
   ```

   예: **EdmUploadAgent.exe /GetSession /DataStoreName PatientRecords**

   상태가 **ProcessingInProgress** 인지 확인합니다. 상태가 **완료** 로 변경될 때까지 몇 분마다 다시 확인하세요. 상태가 완료되면 EDM 데이터를 사용할 수 있습니다. 중요한 정보 원본 테이블 파일의 크기에 따라 몇 분에서 몇 시간까지 걸릴 수 있습니다. 

> [!TIP]
> 업로드된 중요한 데이터를 사용할 준비가 된 후 알림을 받고 싶은 경우 정확한 데이터 일치 활동에 대한 알림 만들기의 [절차를 수행하십시오.](sit-edm-notifications-activities.md#create-notifications-for-exact-data-match-activities)

### <a name="separate-hash-and-upload"></a>별도의 해시 및 업로드

안전한 환경의 컴퓨터에서 해시를 수행합니다. 두 컴퓨터에 **EDMUploadAgent가** 설치되어 있어야 합니다.

선택 사항: 정확한 데이터 일치 schema 및 중요한 정보 유형 마법사를 사용하여 스마마를 만들 때 아직 해당 마법사를 다운로드하지 않은 경우 명령 프롬프트 창에서 다음 명령을 실행하여 파일을 XML 형식으로 다운로드합니다.

```dos
EdmUploadAgent.exe /SaveSchema /DataStoreName <schema name> /OutputDir <path to output folder>
````

1. 보안 환경의 컴퓨터에서 명령 프롬프트 창에서 다음 명령을 실행합니다.

   ```dos
   EdmUploadAgent.exe /CreateHash /DataFile [data file] /HashLocation [hash file location] /Schema [Schema file] /AllowedBadLinesPercentage [value]
   ```

   예시:

   ```dos
   EdmUploadAgent.exe /CreateHash /DataFile C:\Edm\Data\PatientRecords.csv /HashLocation C:\Edm\Hash /Schema edm.xml /AllowedBadLinesPercentage 5
   ```

> [!NOTE]
> 중요한 데이터 파일의 기본 형식은 콤보로 구분된 값입니다. /ColumnSeparator 매개 변수를 사용하여 "{Tab}" 옵션을 지정하여 탭으로 구분된 파일을 지정하거나 "|" 옵션을 지정하여 파이프로 구분된 파일을 지정할 수 있습니다.


   **/Salt <saltvalue>** 옵션을 지정하지 않은 경우 해시 파일과 이러한 확장자를 가진 솔트 파일이 출력됩니다.

   - .EdmHash
   - .EdmSalt


2. 이러한 파일을 안전하게 테넌트에 중요한 정보 원본 테이블 파일(PatientRecords)을 업로드하는 데 사용할 컴퓨터에 복사합니다.

3. EDM 업로드 에이전트에 권한을 설정하고 관리자 권한으로 명령 프롬프트 창을 열고 **C:\EDM\Data** 디렉터리로 전환한 후 다음 명령을 실행합니다.

   `EdmUploadAgent.exe /Authorize`

> [!IMPORTANT]
> **EdmUploadAgent가 설치된 폴더에서 EdmUploadAgent를** 실행하고 데이터 파일의 전체 경로를 지정해야 합니다. 

4. EDM_DataUploaders 보안 그룹에 추가된 Microsoft 365용 회사 또는 학교 계정으로 로그인합니다. 테넌트 정보는 연결을 위해 사용자 계정에서 추출됩니다.

5. 해시된 데이터를 업로드하려면 Windows 명령 프롬프트에서 다음 명령을 실행합니다.

   ```dos
   EdmUploadAgent.exe /UploadHash /DataStoreName \<DataStoreName\> /HashFile \<HashedSourceFilePath\ /ColumnSeparator ["{Tab}"|"|"]
   ```

   예를 들어,

   ```dos
   EdmUploadAgent.exe /UploadHash /DataStoreName PatientRecords /HashFile C:\\Edm\\Hash\\**PatientRecords.EdmHash**
   ```

6. 중요한 데이터가 업로드 되었는지 확인하려면 명령 프롬프트 창에서 다음 명령을 실행합니다.

   ```dos
   EdmUploadAgent.exe /GetDataStore
   ```
   데이터 저장소 목록 및 마지막 업데이트 날짜를 볼 수 있습니다.

7. 특정 저장소에 대한 모든 데이터 업로드를 표시하려면 Windows 명령 프롬프트에서 다음 명령을 실행하여 모든 데이터 저장소의 목록과 업데이트된 시기를 볼 수 있습니다.

   ```dos
   EdmUploadAgent.exe /GetSession /DataStoreName <DataStoreName>
   ```
     
## <a name="next-step"></a>다음 단계

- [정확한 데이터 일치 중요한 정보 유형/규칙 패키지 만들기](sit-get-started-exact-data-match-create-rule-package.md#create-exact-data-match-sensitive-information-typerule-package)

