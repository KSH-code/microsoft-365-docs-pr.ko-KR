---
title: 콘텐츠 검색 결과 내보내기
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
f1_keywords:
- ms.o365.cc.CustomizeExport
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: ed48d448-3714-4c42-85f5-10f75f6a4278
description: 콘텐츠 검색의 검색 결과를 로컬 Microsoft 365 규정 준수 센터 내보낼 수 있습니다. 전자 메일 결과는 PST 파일로 내보낼 수 있습니다. 사이트 SharePoint 비즈니스용 OneDrive 콘텐츠는 기본 Office 내보낼 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 22f66333a5fa2c5b570b564276c626fa0b41f83d
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60662697"
---
# <a name="export-content-search-results"></a>콘텐츠 검색 결과 내보내기

콘텐츠 검색이 성공적으로 실행된 후 검색 결과를 로컬 컴퓨터로 내보낼 수 있습니다. 전자 메일 결과 내보내면 컴퓨터에 PST 파일로 다운로드됩니다. 사이트 및 SharePoint 비즈니스용 OneDrive 내보낼 때 기본 Office 복사본을 내보낼 수 있습니다. 내보낼 검색 결과에 포함된 다른 문서 및 보고서가 있습니다.
  
콘텐츠 검색의 결과를 내보내는 과정에는 결과를 준비한 다음 로컬 컴퓨터에 다운로드해야 합니다. 이러한 검색 결과 내보내기 단계는 Core eDiscovery 사례와 연결된 검색 결과를 내보내는 데도 적용됩니다.
  
## <a name="before-you-export-search-results"></a>검색 결과를 내보내기 전에

- 검색 결과를 내보내기 위해 검색 결과에서 내보내기 관리 역할이 할당되어 Microsoft 365 규정 준수 센터. 이 역할은 기본 제공 eDiscovery 관리자 역할 그룹에 할당됩니다. 기본적으로 조직 관리 역할 그룹에는 할당되지 않습니다. 자세한 내용은 [eDiscovery 권한 할당](assign-ediscovery-permissions.md)을 참조하세요.

- 검색 결과를 PST 파일로 내보내는 데 사용하는 컴퓨터는 다음과 같은 시스템 요구 사항을 충족해야 합니다.
  
  - 최신 버전의 Windows(32비트 또는 64비트)
  
  - Microsoft .NET Framework 4.7 이상
  
- eDiscovery 내보내기 Microsoft Edge 실행하려면<sup>1을</sup> 사용해야 합니다. 검색 Internet Explorer 11을 사용하여 검색 결과를 내보내는 것은 더 이상<sup>지원되지 않습니다 2.</sup>
  
  > [!NOTE]
  > <sup>1</sup> 최신 변경으로 인해 Microsoft Edge ClickOnce 기본적으로 지원이 설정되지 않습니다. Edge에서 ClickOnce 지원을 사용하도록 설정하는 방법에 대한 지침은 에서 [eDiscovery 내보내기 도구 Microsoft Edge.](configure-edge-to-export-search-results.md) 또한 Microsoft는 타사 응용 프로그램용 타사 확장 또는 추가 ClickOnce 않습니다. 타사 확장 또는 추가 기능이 있는 지원되지 않는 브라우저를 사용하여 검색 결과를 내보낼 수 없습니다.
  >
  > <sup>2021년</sup> 8월부터 Microsoft 365 앱 및 서비스에서 IE11(Internet Explorer 11)을 더 이상 지원하지 않고 사용자가 성능이 저하되거나 해당 앱 및 서비스에 연결할 수 없습니다. 이러한 앱 및 서비스는 원활한 지원이 보장될 수 있도록 몇 주 및 몇 개월에 대해 단계적 종료됩니다. 각 앱과 서비스는 독립적인 일정에 따라 단계적으로 운영됩니다. 자세한 내용은 이 블로그 [게시물을 참조하세요.](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-365-apps-say-farewell-to-internet-explorer-11-and/ba-p/1591666)

- 2단계에서 검색 결과를 다운로드하는 데 사용하는 eDiscovery 내보내기 도구는 스크립트를 사용하거나 cmdlet을 실행하여 자동화를 지원하지 않습니다. 1단계의 준비 프로세스나 2단계의 다운로드 프로세스를 자동화하지 않는 것이 좋습니다. 이러한 프로세스 중 하나를 자동화하는 경우 문제가 있는 경우 Microsoft 지원에서 지원을 제공하지 않습니다.

- 검색 결과를 로컬 컴퓨터에 다운로드하는 것이 좋습니다. 검색 결과를 다운로드할 때 회사의 방화벽 또는 프록시 인프라에서 문제를 일으키는 문제를 없애기 위해 네트워크 외부의 가상 데스크톱에 검색 결과를 다운로드하는 것이 좋습니다. 이렇게하면 많은 수의 파일을 내보낼 때 Azure 데이터 연결에서 발생하는 시간 제한이 줄어들 수 있습니다. 가상 데스크톱에 대한 자세한 내용은 가상 [데스크톱 Windows 참조하세요.](https://azure.microsoft.com/services/virtual-desktop)

- 검색 결과를 다운로드할 때 성능을 향상하려면 큰 결과 집합을 작은 검색으로 반환하는 검색을 나중을 고려합니다. 예를 들어 검색 쿼리에서 날짜 범위를 사용하여 더 빠르게 다운로드할 수 있는 더 작은 결과 집합을 반환할 수 있습니다.
  
- 검색 결과를 내보낼 때 데이터는 로컬 컴퓨터로 다운로드되기 전에 Microsoft 클라우드의 Azure Storage Microsoft 제공 위치에 일시적으로 저장됩니다. 조직에서 **\* .blob.core.windows.net** Azure의 끝점에 연결할 수 있는지 확인(와일드카드는 내보내기 고유 식별자를 나타임) 검색 결과 데이터는 생성된 Azure Storage 위치에서 삭제됩니다. 
  
- 조직에서 프록시 서버를 사용하여 인터넷과 통신하는 경우 검색 결과를 내보내는 데 사용하는 컴퓨터에서 프록시 서버 설정을 정의해야 합니다(내보내기 도구를 프록시 서버에서 인증할 수 있도록). 이렇게 하여machine.config 버전과 일치하는 위치에서 Windows. 
  
  - **32비트:** `%windir%\Microsoft.NET\Framework\[version]\Config\machine.config`
  
  - **64비트:** `%windir%\Microsoft.NET\Framework64\[version]\Config\machine.config`
  
    및 태그 사이의machine.config *파일에*  다음  `<configuration>`  `</configuration>` 줄을 추가합니다. 조직에 대한 올바른 값(예: )으로  `ProxyServer`  `Port` 바꾸어야 `proxy01.contoso.com:80` 합니다. 
  
    ```xml
    <system.net>
       <defaultProxy enabled="true" useDefaultCredentials="true">
         <proxy proxyaddress="https://ProxyServer :Port " 
                usesystemdefault="False" 
                bypassonlocal="True" 
                autoDetect="False" />
       </defaultProxy>
    </system.net>
    ```

- 검색 결과가 7일보다 오래된 경우 내보내기 작업을 제출하면 검색을 다시 시작하여 검색 결과를 업데이트하라는 오류 메시지가 표시됩니다. 이 경우 내보내기 작업을 취소하고 검색을 다시 시작한 다음 내보내기 작업을 다시 시작하십시오.

## <a name="step-1-prepare-search-results-for-export"></a>1단계: 검색 결과 내보내기 준비

첫 번째 단계는 검색 결과의 내보내기를 준비하는 것입니다. 결과를 준비하면 Microsoft 클라우드의 Microsoft Azure Storage 위치에 업로드됩니다. 사서함 및 사이트의 콘텐츠는 시간당 최대 2GB의 속도로 업로드됩니다.
  
1. 다음 Microsoft 365 규정 준수 센터 검색에서 결과를 내보낼 콘텐츠 검색을 선택합니다.
  
2. **플라이아웃** 페이지의 아래쪽에 있는 작업 메뉴에서 결과 **내보내기 를 클릭합니다.**

   ![작업 메뉴에서 결과 내보내기 옵션입니다.](../media/ActionMenuExportResults.png)

   결과 **내보내기** 플라이아웃 페이지가 표시됩니다. 콘텐츠를 내보내는 데 사용할 수 있는 내보내기 옵션은 검색 결과가 사서함에 있는지 사이트인지 아니면 둘의 조합인지에 따라 결정됩니다.

3. 출력 **옵션에서** 다음 옵션 중 하나를 선택합니다.
  
   ![출력 옵션을 내보낼 수 있습니다.](../media/ExportOutputOptions.png)

    - **인식할** 수 없는 형식의 항목을 제외한 모든 항목은 암호화되거나 다른 이유로 인덱싱되지 않습니다. 이 옵션은 인덱싱된 항목만 내보낼 수 있습니다.
  
    - 인식할 수 없는 형식을 포함한 모든 항목은 암호화되거나 다른 이유로 인덱싱되지 **않은 항목입니다.** 이 옵션은 인덱싱된 항목과 인덱싱되지 않은 항목을 내보낼 수 있습니다.
  
    - **인식할 수 없는** 형식의 항목만 암호화되거나 다른 이유로 인덱싱되지 않은 항목만 이 옵션은 인덱서되지 않은 항목만 내보낼 수 있습니다.

      부분적으로 [인덱싱된](#more-information) 항목을 내보내는 방법에 대한 설명은 추가 정보 섹션을 참조하세요. 부분적으로 인덱싱된 항목에 대한 자세한 내용은 콘텐츠 검색에서 [부분적으로 인덱싱된 항목을 참조하세요.](partially-indexed-items-in-content-search.md)

4. 콘텐츠 **Exchange 내보내기에서** 다음 옵션 중 하나를 선택합니다.
  
   ![Exchange 옵션을 선택합니다.](../media/ExchangeExportOptions.png)

    - **각 사서함에 대해 하나의 PST 파일:** 검색 결과가 포함된 각 사용자 사서함에 대해 하나의 PST 파일을 내보낼 수 있습니다. 사용자의 보관 사서함의 모든 결과는 동일한 PST 파일에 포함됩니다. 이 옵션은 원본 사서함에서 사서함 폴더 구조를 재현합니다.
  
    - **모든 메시지를** 포함하는 PST 파일 하나: 검색에 포함된 모든 원본 사서함의 검색 결과를 포함하는 단일 PST 파일(Exchange.pst)을 내보낼 수 있습니다.  이 옵션은 각 메시지에 대한 사서함 폴더 구조를 재현합니다.
  
    - **단일 폴더에** 모든 메시지를 포함하는 PST 파일 하나: 모든 메시지가 단일 최상위 폴더에 있는 단일 PST 파일로 검색 결과를 내보낼 수 있습니다. 이 옵션을 사용하면 검토자는 각 항목의 원래 사서함 폴더 구조를 탐색하지 않고도 항목을 시간 순서(항목이 보낸 날짜별로 정렬)하여 검토할 수 있습니다.
  
    - **개별 메시지:**.msg 형식을 사용하여 검색 결과를 개별 전자 메일 메시지로 내보낼 수 있습니다. 이 옵션을 선택하면 파일 시스템의 폴더로 전자 메일 검색 결과를 내보낼 수 있습니다. 개별 메시지의 폴더 경로는 결과를 PST 파일로 내보낼 때 사용한 경로와 동일합니다.
  
5. 다음과 같은 추가 옵션을 구성합니다.

   ![다른 내보내기 옵션을 구성합니다.](../media/OtherExportOptions.png)

   1. 중복 **메시지를** 제외하려면 콘텐츠에 Exchange 사용 확인란을 선택합니다.
  
      이 옵션을 선택하면 검색된 사서함에서 동일한 메시지의 복사본이 여러 개 발견된 경우에도 메시지 복사본이 하나만 내보낼 수 있습니다. 내보내기 결과 보고서(Results.csv 파일)에는 중복 메시지의 복사본이 포함된 사서함(또는 공용 폴더)을 식별할 수 있도록 중복 메시지의 모든 복사본에 대한 행이 포함되어 있습니다. 중복 제거 및 중복 항목을 식별하는 방법에 대한 자세한 내용은 [eDiscovery](de-duplication-in-ediscovery-search-results.md)검색 결과에서 중복 제거를 참조하세요.
  
   2. 모든 버전의 파일을 **SharePoint 파일** 포함 확인란을 선택하여 모든 버전의 SharePoint 내보낼 수 있습니다. 이 옵션은 검색의 콘텐츠 원본에 사이트 또는 사이트가 포함된 SharePoint 비즈니스용 OneDrive 표시됩니다.
  
   3. 압축된(zip) 폴더에서 파일 **내보내기를 선택합니다. 검색 결과를** 압축된 폴더로 내보내기 위한 개별 메시지와 SharePoint 확인란만 포함합니다. 이 옵션은 개별 메시지로 Exchange 내보낼 때 그리고 검색 결과에 문서 또는 문서의 SharePoint OneDrive 표시됩니다. 이 옵션은 주로 항목을 내보낼 때 파일 경로 Windows 260자 제한을 사용하는 데 사용됩니다. 자세한 내용은 추가 정보 섹션에서 "내보낼 항목의 [파일 이름"을 참조하세요.](#more-information)
   > [!IMPORTANT]
   > 압축된(압축된) 폴더에 파일을 내보내면 내보내기 시간도 늘어날 수 있습니다.
  
6. 내보내기 **를** 클릭하여 내보내기 프로세스를 시작합니다. 검색 결과는 다운로드할 수 있습니다. 즉, 원래 콘텐츠 위치에서 수집된 다음 Microsoft 클라우드의 Azure Storage 위치로 업로드됩니다. 이 작업에는 몇 분이 걸릴 수 있습니다.

내보낼 검색 결과를 다운로드하는 방법에 대한 지침은 다음 섹션을 참조하세요.
  
## <a name="step-2-download-the-search-results"></a>2단계: 검색 결과 다운로드

다음 단계는 검색 결과를 로컬 컴퓨터로 Azure Storage 다운로드하는 것입니다.

> [!NOTE]
> 내보낼 검색 결과는 1단계에서 내보내기 작업을 만든 후 14일 이내에 다운로드해야 합니다.
  
1. 콘텐츠 **검색 페이지의** Microsoft 365 규정 준수 센터 **내보내기 탭을** 선택합니다.
  
   새로 고침을 **클릭하여** 만든 내보내기 작업이 표시될 수 있도록 내보내기 작업 목록을 업데이트해야 할 수 있습니다. 내보내기 작업의 이름은 검색 이름에  추가된 _Export 검색과 동일합니다.
  
2. 1단계에서 만든 내보내기 작업을 선택합니다.

3. 내보내기 키 아래의 플라이아웃 페이지에서 **클립보드에 복사를 클릭합니다.** 6단계에서 이 키를 사용하여 검색 결과를 다운로드합니다.
  
   > [!IMPORTANT]
   > 누구나 eDiscovery 내보내기 도구를 설치하여 시작하고 이 키를 사용하여 검색 결과를 다운로드할 수 있으므로 암호나 기타 보안 관련 정보를 보호할 때처럼 이 키를 주의해서 보호해야 합니다.

4. 플라이아웃 페이지 위쪽에서 결과 다운로드 **를 클릭합니다.**

5. **eDiscovery** 내보내기 도구를 설치하라는 메시지가 표시될 경우 설치를 **클릭합니다.**

6. **eDiscovery 내보내기 도구에서** 다음을 실행합니다.

   ![eDiscovery 내보내기 도구.](../media/eDiscoveryExportTool.png)

   1. 3단계에서 복사한 내보내기 키를 해당 상자에 붙여 넣습니다.
  
   2. **찾아보기** 를 클릭하여 검색 결과 파일을 다운로드하려는 위치를 지정합니다.
  
      > [!IMPORTANT]
      >  다운로드하는 동안 네트워크 활동이 높기 때문에 로컬 컴퓨터의 내부 드라이브에 있는 위치로만 검색 결과를 다운로드해야 합니다. 최상의 다운로드 환경을 위해 다음 지침을 따르세요. <br/>
      >- 검색 결과를 UNC 경로, 매핑된 네트워크 드라이브, 외부 USB 드라이브 또는 동기화된 계정으로 비즈니스용 OneDrive 않습니다.<br/>
      >- 검색 결과를 다운로드하는 폴더에 대해 바이러스 백신 검색을 사용하지 않도록 설정하십시오.<br/>
      >- 검색 결과를 여러 폴더에 다운로드하여 동시 다운로드 작업을 합니다.

7. **시작** 을 클릭하여 컴퓨터에 검색 결과를 다운로드합니다.
  
    **eDiscovery 내보내기 도구** 는 다운로드할 남은 항목의 예상 개수(크기)를 포함하여 내보내기 프로세스에 대한 상태 정보를 표시합니다. 내보내기 프로세스가 완료되면 다운로드된 위치에서 파일에 액세스할 수 있습니다.

## <a name="more-information"></a>자세한 정보

검색 결과 내보내기에 대한 자세한 내용은 다음과 같은 정보를 제공합니다.
  
[내보내기 제한](#export-limits)
  
[보고서 내보내기](#export-reports)
  
[부분적으로 인덱싱된 항목 내보내기](#exporting-partially-indexed-items)

[개별 메시지 또는 PST 파일 내보내기](#exporting-individual-messages-or-pst-files)

[RMS로 보호된 전자 메일 메시지 및 암호화된 첨부 파일 암호 해독](#decrypting-rms-protected-email-messages-and-encrypted-file-attachments)

[내보낼 항목의 파일 이름](#filenames-of-exported-items)  
  
[기타](#miscellaneous)
  
### <a name="export-limits"></a>내보내기 제한

콘텐츠 검색 결과를 내보낼 때의 제한에 대한 자세한 내용은 콘텐츠 검색 제한의 "내보내기 제한" [섹션을 참조하세요.](limits-for-content-search.md#export-limits)

### <a name="export-reports"></a>보고서 내보내기
  
- 검색 결과를 내보낼 때 검색 결과와 함께 다음 보고서가 포함됩니다.
  
  - **요약 내보내기** 내보내기 Excel 포함된 문서입니다. 여기에는 검색된 콘텐츠 원본 수, 검색 결과의 예상 및 다운로드 크기, 내보낼 예상 및 다운로드한 항목 수 등의 정보가 포함됩니다.
  
  - **매니페스트** 검색 결과에 포함된 각 항목에 대한 정보가 포함된 매니페스트 파일(XML 형식)입니다.
  
  - **결과** 검색 Excel 다운로드하는 각 항목에 대한 정보가 포함된 문서입니다. 전자 메일의 경우 결과 로그에는 다음을 비롯한 각 메시지에 대한 정보가 포함되어 있습니다.
  
    - 원본 사서함에 있는 메시지의 위치 (포함 여부는 주 메시지는 보관 사서함 또는).
  
    - 메시지가 전송된 날짜

    - 메시지의 제목 줄입니다.

    - 보낸 사람 및 메시지 받는 사람입니다.

    - 검색 결과를 내보낼 때 중복 제거 옵션을 사용하도록 설정한 경우 메시지가 중복 메시지인지 여부입니다. 중복 메시지에는 해당 메시지를  중복 항목으로 식별하는 항목이 중복 열에 있습니다. 항목에 중복 **열의 값에는** 내보낼 메시지의 항목 ID가 포함되어 있습니다. 자세한 내용은 [eDiscovery 검색 결과에서 중복 제거를 참조하세요.](de-duplication-in-ediscovery-search-results.md)

      사이트 및 SharePoint 비즈니스용 OneDrive 문서의 경우 결과 로그에는 다음을 비롯한 각 문서에 대한 정보가 들어 있습니다.

      - 문서에 대 한 URL입니다.

      - 문서가 있는 사이트 모음의 URL입니다.

      - 문서를 마지막으로 수정한 날짜입니다.

      - 이름 (에 있는 제목 열 결과 로그에서) 문서입니다.

  - **인덱서되지 않은 항목** 검색 Excel 부분적으로 인덱싱된 항목에 대한 정보가 포함된 문서입니다. 검색 결과 보고서를 생성할 때 부분적으로 인덱싱된 항목을 포함하지 않는 경우 이 보고서는 계속 다운로드되지만 비어 있습니다.

  - **오류 및 경고** 내보내기 중에 발생하는 파일에 대한 오류 및 경고가 들어 있습니다. 각 오류 또는 경고에 대한 자세한 내용은 오류 세부 정보 열을 참조하세요.

  - **건너뛴 항목** 사이트 및 SharePoint 비즈니스용 OneDrive 내보내는 경우 내보내기에는 일반적으로 건너뛴 항목 보고서(SkippedItems.csv)가 포함됩니다. 이 보고서에 인용된 항목은 일반적으로 폴더나 문서 집합과 같이 다운로드되지 않는 항목입니다. 이러한 유형의 항목은 내보낼 수 없습니다. 건너뛴 다른 항목의 경우 건너뛴 항목 보고서의 '오류 유형' 및 '오류 세부 정보' 필드에는 항목을 건너뛴 이유와 다른 검색 결과와 함께 다운로드되지 않은 이유가 표시됩니다.

  - **Trace.log** 내보내기 프로세스에 대한 자세한 로깅 정보를 포함하며 내보내기 중에 문제를 쉽게 확인 할 수 있습니다. 검색 결과 내보내기와 관련된 문제와 관련된 Microsoft 지원 티켓을 여는 경우 이 추적 로그를 제공해야 할 수 있습니다.
  
    > [!NOTE]
    > 이러한 문서는 실제 검색 결과를 내보낼 필요 없이 내보낼 수 있습니다. 콘텐츠 [검색 보고서 내보내기 를 참조하세요.](export-a-content-search-report.md)
  
### <a name="exporting-partially-indexed-items"></a>부분적으로 인덱싱된 항목 내보내기
  
- 검색 쿼리에 포함된 키워드가 없는 경우 검색 결과의 모든 사서함 항목을 반환하는 콘텐츠 검색에서 사서함 항목을 내보내는 경우 부분적으로 인덱싱된 항목은 인덱싱되지 않은 항목이 포함된 PST 파일에 복사되지 않습니다. 부분적으로 인덱싱된 항목을 포함하여 모든 항목이 일반 검색 결과에 자동으로 포함하기 때문에입니다. 즉, 부분적으로 인덱싱된 항목은 다른 인덱싱된 항목이 포함된 PST 파일(또는 개별 메시지)에 포함됩니다.

    인덱싱된 항목과 부분적으로 인덱싱된 항목을 모두 내보내거나 모든 항목을 반환하는 콘텐츠 검색에서 인덱싱된 항목만 내보내면 동일한 수의 항목이 다운로드됩니다. 콘텐츠 검색에 대한 예상 검색 결과(Microsoft 365 규정 준수 센터 검색 통계에 표시)에 부분적으로 인덱싱된 항목 수에 대한 별도의 예상치가 포함되는 경우에도 이러한 상황이 발생합니다. 예를 들어 모든 항목을 포함하는 검색의 예상 결과(검색 쿼리의 키워드 없음)는 1,000개 항목이 발견된 것으로 표시하고 부분적으로 인덱싱된 항목 200개도 발견된 것으로 나타났습니다. 이 경우 1,000개 항목에는 부분적으로 인덱싱된 항목이 포함됩니다. 검색 시 모든 항목이 반환됩니다. 즉, 검색에서 반환된 총 항목이 1,000개가 있으며 1,200개 항목은 반환되지 않습니다(예상한 수만큼). 이 검색 결과를 내보내고 인덱싱된 항목과 부분적으로 인덱싱된 항목을 내보내거나 부분적으로 인덱싱된 항목만 내보내면 1,000개 항목이 다운로드됩니다. 이는 빈 검색 쿼리를 사용하여 모든 항목을 반환할 때 부분적으로 인덱싱된 항목이 일반(인덱싱된) 결과에 포함하기 때문에 그 결과입니다. 이 예에서 부분적으로 인덱싱된 항목만 내보내면 인덱싱되지 않은 항목 200개만 다운로드됩니다.

    또한 이전 예제에서(인덱싱된 항목과 부분적으로 인덱싱된 항목을 내보내거나  인덱싱된 항목만 내보낼 경우) 내보낼 수 있는 검색 결과에 포함된 요약 내보내기 보고서에는 앞서 설명한 동일한 이유로 예상 항목 1,000개와 다운로드된 항목 1,000개가 나열됩니다. 

- 결과를 내보낼 검색이 특정 콘텐츠 위치 또는 조직의 모든 콘텐츠 위치를 검색한 경우 검색 조건과 일치하는 항목이 포함된 콘텐츠 위치의 부분 항목만 내보내기됩니다. 즉, 사서함이나 사이트에서 검색 결과를 찾을 수 없는 경우 해당 사서함 또는 사이트의 부분적으로 인덱싱된 항목은 내보내지 않습니다. 그 이유는 조직의 여러 위치에서 부분적으로 인덱싱된 항목을 내보내면 내보내기 오류 발생 가능성이 높아지며 검색 결과를 내보내고 다운로드하는 데 걸리는 시간이 늘어날 수 있습니다.

    검색에 대한 모든 콘텐츠 위치에서 부분적으로 인덱싱된 항목을 내보내기 위해 검색 쿼리에서 키워드를 제거하여 모든 항목을 반환하도록 검색을 구성한 다음 검색 결과를 내보낼 때 부분적으로 인덱싱된 항목만 내보낼 수 있습니다.

    ![세 번째 내보내기 옵션을 사용하여 인덱서되지 않은 항목만 내보낼 수 있습니다.](../media/5d7be338-a0e5-425f-8ba5-92769c24bf75.png)
  
- SharePoint 또는 비즈니스용 OneDrive 사이트에서 검색 결과를 내보낼 때 인덱싱되지 않은 항목을 내보내는 능력은 선택한 내보내기 옵션과 검색된 사이트에 검색 조건과 일치하는 인덱싱된 항목이 포함되어 있는지 여부에 따라 결정됩니다. 예를 들어 특정 SharePoint 또는 비즈니스용 OneDrive 사이트를 검색하고 검색 결과를 찾을 수 없는 경우 인덱싱된 항목과 인덱싱되지 않은 항목을 모두 내보내기 위한 두 번째 내보내기 옵션을 선택하면 해당 사이트에서 인덱싱되지 않은 항목이 내보내지 않습니다. 사이트에서 인덱싱된 항목이 검색 조건과 일치하면 인덱싱된 항목과 인덱싱되지 않은 항목을 모두 내보낼 때 해당 사이트의 인덱싱되지 않은 모든 항목이 내보내됩니다. 다음 그림에서는 사이트에 검색 조건과 일치하는 인덱싱된 항목이 포함되어 있는지 여부에 따라 내보내기 옵션에 대해 설명합니다.

    ![사이트에 검색 조건과 일치하는 인덱싱된 항목이 포함되어 있는지 여부에 따라 내보내기 옵션을 선택합니다.](../media/94f78786-c6bb-42fb-96b3-7ea3998bcd39.png)

    a. 검색 조건과 일치하는 인덱싱된 항목만 내보낼 수 있습니다. 부분적으로 인덱싱된 항목은 내보내지 않습니다.

    b. 사이트의 인덱싱된 항목이 검색 조건과 일치하지 않는 경우 동일한 사이트의 부분적으로 인덱싱된 항목은 내보내지 않습니다. 사이트의 인덱싱된 항목이 검색 결과에 반환되는 경우 해당 사이트의 부분적으로 인덱싱된 항목을 내보낼 수 있습니다. 즉, 검색 조건과 일치하는 항목이 포함된 사이트에서 부분적으로 인덱싱된 항목만 내보낼 수 있습니다.

    c. 사이트에 검색 조건과 일치하는 항목이 포함되어 있는지 여부에 관계없이 검색의 모든 사이트에서 부분적으로 인덱싱된 모든 항목을 내보낼 수 있습니다.

    부분적으로 인덱싱된 항목을 내보내면 부분적으로 인덱싱된 사서함 항목이 다른 PST 파일로 내보내기에서 선택한 옵션에 관계없이 Exchange **내보낼 수 있습니다.**

- 부분적으로 인덱싱된 항목의 다른 속성이 검색 조건과 일치하기 때문에 검색 결과에 부분적으로 인덱싱된 항목이 반환되는 경우 부분적으로 인덱싱된 항목은 일반 검색 결과와 함께 내보낼 수 있습니다. 따라서 인덱싱된 항목과 부분적으로 인덱싱된 항목을 모두  내보낼 경우(인식할 수 없는 형식이 있는 항목, 암호화되거나 다른 이유로 인덱싱되지 않은 항목 포함) 일반 결과로 내보내는 부분적으로 인덱싱된 항목이 Results.csv 보고서에 나열됩니다. 이러한 목록은 인덱서되지 않은 보고서에 items.csv 않습니다.
  
### <a name="exporting-individual-messages-or-pst-files"></a>개별 메시지 또는 PST 파일 내보내기
  
- 메시지의 파일 경로 이름이 메시지의 최대 문자 Windows 초과하면 파일 경로 이름이 트렁크됩니다. 그러나 원래 파일 경로 이름은 매니페스트 및 ResultsLog에 나열됩니다.
  
- 앞서 설명한 것 처럼 전자 메일 검색 결과는 파일 시스템의 폴더로 내보낼 수 있습니다. 개별 메시지의 폴더 경로는 사용자 사서함의 폴더 경로를 복제합니다. 예를 들어 사용자의 받은 편지함에서 "ContosoCase101"이라는 검색의 경우 폴더 경로 에  `~ContosoCase101\\<date of export\Exchange\user@contoso.com (Primary)\Top of Information Store\Inbox` 있습니다.

- 단일 폴더의 모든 메시지를 포함하는 하나의 PST 파일에서 전자 메일  메시지를 내보내면 지우기 항목 폴더와 검색 폴더가 PST 폴더의 최상위 수준에 포함됩니다.  이러한 폴더는 비어 있습니다.

- 앞서 설명한 것 처럼 전자 메일 검색 결과를 개별 메시지로 내보내 RMS로 보호된 메시지를 내보낼 때 암호를 해독해야 합니다. 전자 메일 검색 결과를 PST 파일로 내보낼 경우 암호화된 메시지는 암호화된 상태로 유지됩니다.
  
### <a name="decrypting-rms-protected-email-messages-and-encrypted-file-attachments"></a>RMS로 보호된 전자 메일 메시지 및 암호화된 첨부 파일 암호 해독

콘텐츠 검색 결과에 포함된 권한으로 보호된(RMS로 보호된) 전자 메일 메시지는 내보낼 때 암호가 해독됩니다. 또한 [Microsoft](encryption.md) 암호화 기술로 암호화되고 검색 결과에 포함된 전자 메일 메시지에 첨부된 모든 파일은 내보낼 때도 암호 해독됩니다. 이 암호 해독 기능은 기본적으로 eDiscovery 관리자 역할 그룹의 구성원에 대해 사용하도록 설정됩니다. 이는 기본적으로 RMS 암호 해독 관리 역할이 이 역할 그룹에 할당되어 있기 때문에입니다. 암호화된 전자 메일 메시지 및 첨부 파일을 내보낼 때 다음에 유의하세요.
  
- 앞서 설명한 것 처럼 RMS로 보호된 메시지를 내보낼 때 암호를 해독하기 위해 검색 결과를 개별 메시지로 내보내야 합니다. 검색 결과를 PST 파일로 내보낼 경우 RMS로 보호된 메시지는 암호화된 상태로 유지됩니다.

- 암호 해독된 메시지는 **ResultsLog** 보고서에서 식별됩니다. 이 보고서에는 **디코드** 상태라는 열이 포함되어 있으며 이 열의 **디코드** 값은 암호 해독된 메시지를 식별합니다.

- 검색 결과를 내보낼 때 첨부 파일의 암호를 해독하는 것 외에도 검색 결과를 미리 볼 때 암호 해독된 파일을 미리 볼 수도 있습니다. 권한으로 보호된 전자 메일 메시지는 내보낼 때만 볼 수 있습니다.

- 현재 검색 결과를 내보낼 때의 암호 해독 기능에는 검색 결과 및 SharePoint 암호화된 콘텐츠가 비즈니스용 OneDrive 않습니다. 그러나 Microsoft 암호화 기술로 암호화되고 온라인 및 SharePoint 문서에 대한 지원이 비즈니스용 OneDrive.

- RMS로 보호되는 메시지 및 암호화된 첨부 파일의 암호를 해독하지 못하도록 해야 하는 경우 기본 제공 eDiscovery 관리자 역할 그룹을 복사하여 사용자 지정 역할 그룹을 만든 다음 사용자 지정 역할 그룹에서 RMS 암호 해독 관리 역할을 제거해야 합니다. 그런 다음 메시지의 암호를 해독하지 않는 사람을 사용자 지정 역할 그룹의 구성원으로 추가합니다.
  
### <a name="filenames-of-exported-items"></a>내보낼 항목의 파일 이름
  
- 로컬 컴퓨터로 내보낼 전자 메일 메시지 및 사이트 문서의 전체 경로 이름에는 260자 제한이 있습니다(운영 체제에서 부과). 내보낼 항목의 전체 경로 이름에는 항목의 원래 위치와 검색 결과가 다운로드되는 로컬 컴퓨터의 폴더 위치가 포함됩니다. 예를 들어 eDiscovery 내보내기 도구에서 검색 결과를 다운로드하기로 지정한 경우 다운로드한 전자 메일 항목의 전체 경로 이름은  `C:\Users\Admin\Desktop\SearchResults`  `C:\Users\Admin\Desktop\SearchResults\ContentSearch1\03.15.2017-1242PM\Exchange\sarad@contoso.com (Primary)\Top of Information Store\Inbox\Insider trading investigation.msg` 입니다.

- 260자 제한을 초과하면 항목의 전체 경로 이름이 다음을 기준으로 하여 길이가 희미해지게 됩니다.

  - 전체 경로 이름이 260자보다 길면 파일 이름이 제한에 따라 단축됩니다. 잘라 내는 파일 이름(파일 확장명 제외)은 8자 미만이 됩니다.

  - 파일 이름을 짧게 지정한 후에도 전체 경로 이름이 너무 길면 항목이 현재 위치에서 상위 폴더로 이동됩니다. 경로 이름의 길이가 너무 길면 파일 이름을 단축하고 필요한 경우 다시 상위 폴더로 이동하는 프로세스가 반복됩니다. 이 프로세스는 전체 경로 이름을 260자 제한에 도달할 때까지 반복됩니다.

  - 전체 경로 이름이 이미 있으면 파일 이름 끝에 버전 번호가 추가됩니다. 예를 들면 `statusmessage(2).msg` 입니다.

    이 문제를 완화하려면 짧은 경로 이름이 있는 위치에 검색 결과를 다운로드하는 것이 좋습니다. 예를 들어 이라는 폴더에 검색 결과를 다운로드하면 내보낼 항목의 경로 이름에 이라는 폴더에 다운로드하는 것보다 더 적은 문자가  `C:\Results`  `C:\Users\Admin\Desktop\Results` 추가됩니다.

- 사이트 문서를 내보낼 때 문서의 원래 파일 이름을 수정할 수도 있습니다. 이 문제는 보류된 사이트 또는 SharePoint 비즈니스용 OneDrive 삭제된 문서에 대해 구체적으로 발생합니다. 보류 상태인 사이트에 있는 문서가 삭제되면 삭제된 문서가 사이트의 자료 보존 라이브러리(사이트가 보류 중일 때 만들어진 자료 보존 라이브러리)로 자동으로 이동됩니다. 삭제된 문서를 자료 보존 라이브러리로 이동하면 임의로 생성되고 고유한 ID가 문서의 원래 파일 이름에 추가됩니다. 예를 들어 문서의 파일 이름을 나중에 삭제하고 자료 보존 라이브러리로 이동하면 자료 보존 라이브러리로 이동한 문서의 파일 이름을 과 같이  `FY2017Budget.xlsx`  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` 수정합니다. 자료 보존 라이브러리의 문서가 콘텐츠 검색의 쿼리와 일치하고 해당 검색 결과를 내보낼 경우 내보낼 파일에 수정된 파일 이름도 있습니다. 이 예제에서 내보낼 문서의 파일 이름은  `FY2017Budget_DEAF727D-0478-4A7F-87DE-5487F033C81A2000-07-05T10-37-55.xlsx` 입니다.

    보류된 사이트의 문서가 수정되고 사이트의 문서 라이브러리에 대한 버전이 설정되면 자료 보존 라이브러리에 파일의 복사본이 자동으로 만들어집니다. 이 경우 임의로 생성된 고유 ID도 자료 보존 라이브러리에 복사된 문서의 파일 이름에 추가됩니다.

    자료 보존 라이브러리로 이동되거나 복사되는 문서의 파일 이름을 변경하는 이유는 파일 이름 충돌을 방지하기 위한 것입니다. 사이트 및 자료 보존 라이브러리에 보류를 설정하는 자세한 내용은 [Overview of in-place hold in SharePoint Server 2016를 참조하십시오.](https://support.office.com/article/5e400d68-cd51-444a-8fe6-e4df1d20aa95)

### <a name="miscellaneous"></a>기타
  
- eDiscovery 내보내기 도구를 사용하여 검색 결과를 다운로드할 때 다음과 같은 오류가 발생할 수 있습니다. 이 오류는 일반적으로 Azure Storage `System.Net.WebException: The remote server returned an error: (412) The condition specified using HTTP conditional header(s) is not met.` 오류입니다. 이 문제를 해결하려면 eDiscovery 내보내기 도구를 다시 시작하는 검색 결과 다운로드를 다시 시도합니다. [](#step-2-download-the-search-results)

- 모든 검색 결과 및 내보내기 보고서는 콘텐츠 검색과 이름이 같은 폴더에 포함됩니다. 내보낸 전자 메일 메시지는 **Exchange** 라는 폴더에 있습니다. 문서는 **SharePoint** 라는 폴더에 있습니다.

- 로컬 컴퓨터로 문서를 내보낼 때 SharePoint 비즈니스용 OneDrive 사이트의 문서에 대한 파일 시스템 메타데이터가 유지 관리됩니다. 즉, 만든 날짜 및 마지막으로 수정한 날짜와 같은 문서 속성은 문서를 내보낼 때도 변경되지 않습니다.

- 검색 결과에 검색 쿼리와 일치하는 SharePoint 목록 항목이 포함된 경우 목록의 모든 행과 검색 쿼리 및 목록의 첨부 파일과 일치하는 항목이 모두 내보내집니다. 이 동작의 이유는 검색 결과에 반환되는 목록 항목에 대한 컨텍스트를 제공하기 위한 것입니다. 추가 목록 항목 및 첨부 파일로 인해 내보낼 항목 수가 원래 예상 검색 결과와 다를 수 있습니다.
