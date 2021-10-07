---
title: 외부 연락처를 대량으로 Exchange Online
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
audience: End User
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid:
- MET150
- MOP150
ms.assetid: bed936bc-0969-4a6d-a7a5-66305c14e958
description: 관리자가 PowerShell 및 CSV Exchange Online 사용하여 외부 연락처를 전체 주소 목록으로 대량으로 가져올 수 있는 방법을 알아보습니다.
ms.openlocfilehash: 399534a74a7245ebb71624b390343c81e692925e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60170862"
---
# <a name="bulk-import-external-contacts-to-exchange-online"></a>외부 연락처를 대량으로 Exchange Online

**이 문서는 관리자를 위한 것입니다. 자신의 사서함으로 연락처를 가져오려고 하나요? 연락처 [가져오기 및 Outlook](https://support.office.com/article/bb796340-b58a-46c1-90c7-b549b8f3c5f8)**
   
회사에 공유 주소 목록(전체 주소 목록)에 포함하려는 기존 비즈니스 연락처가 Exchange Online. 회사 내부의 사용자와 마찬가지로 외부 연락처를 메일 그룹의 구성원으로 추가하고 싶나요? 이 경우 PowerShell 및 CSV(Exchange Online 값) 파일을 사용하여 외부 연락처를 여러 개의 파일로 대량으로 가져올 Exchange Online. 3단계 프로세스입니다.
  
[1단계: 외부 연락처에 대한 정보가 포함된 CSV 파일 만들기](#step-1-create-a-csv-file-that-contains-information-about-the-external-contacts)

[2단계: PowerShell을 사용하여 외부 연락처 만들기](#step-2-create-the-external-contacts-with-powershell) 

[3단계: 외부 연락처의 속성에 정보 추가](#step-3-add-information-to-the-properties-of-the-external-contacts)

이러한 단계를 완료하여 연락처를 가져온 후 다음 추가 작업을 수행할 수 있습니다.
  
- [외부 연락처 추가](#add-more-external-contacts)
  
- [공유 주소 책에서 외부 연락처 숨기기](#hide-external-contacts-from-the-shared-address-book)
  
## <a name="step-1-create-a-csv-file-that-contains-information-about-the-external-contacts"></a>1단계: 외부 연락처에 대한 정보가 포함된 CSV 파일 만들기

첫 번째 단계는 가져오기 위해 가져올 각 외부 연락처에 대한 정보가 포함된 CSV 파일을 Exchange Online. 
  
1. 다음 텍스트를 메모장의 텍스트 파일에 복사하고 파일 이름 접미사로 를 사용하여 데스크톱에 CSV 파일로 .csv. 예를 들어 ExternalContacts.csv.
    
    > [!TIP]
    > 언어에 특수 문자(예: **å,** **ä**, **ö)가** 포함되어 있는 경우 메모장에 파일을 저장할 때 CSV 파일을 UTF-8 또는 기타 유니코드 인코딩으로 저장합니다. 
  
    ```text
    ExternalEmailAddress,Name,FirstName,LastName,StreetAddress,City,StateorProvince,PostalCode,Phone,MobilePhone,Pager,HomePhone,Company,Title,OtherTelephone,Department,CountryOrRegion,Fax,Initials,Notes,Office,Manager
    danp@fabrikam.com,Dan Park,Dan,Park,1234 23rd Ave,Golden,CO,80215,206-111-1234,303-900-1234,555-1212,123-456-7890,Fabrikam,Shipping clerk,555-5555,Shipping,US,123-4567,R.,Good worker,31/1663,Dan Park
    pilar@contoso.com,Pilar Pinilla,Pilar,Pinilla,1234 Main St.,Seattle,WA,98017,206-555-0100,206-555-0101,206-555-0102,206-555-1234,Contoso,HR Manager,206-555-0104,Executive,US,206-555-0105,P.,Technical decision maker,31/1000,Dan Park
    ```

    CSV 파일의 첫 번째 행(머리줄 행)에는 연락처를 가져올 때 사용할 수 있는 연락처의 속성이 Exchange Online. 각 속성 이름은 콤보로 구분됩니다. 머리줄 행 아래에 있는 각 행은 단일 외부 연락처를 가져오기 위한 속성 값을 나타냅니다. 
    
    > [!NOTE]
    > 이 텍스트에는 삭제할 수 있는 예제 데이터가 포함됩니다. 그러나 첫 번째(헤더) 행은 삭제하거나 변경하지 않습니다. 외부 연락처의 모든 속성이 들어 있습니다. 
  
2. CSV 파일을 Microsoft Excel CSV 파일을 편집하는 것이 훨씬 더 쉬우기 때문에 CSV 파일을 Excel 파일을 열 수 있습니다.
    
3. 연락처로 가져올 각 연락처에 대한 행을 Exchange Online. 가능한 한 많은 셀을 채우십시오. 이 정보는 각 연락처의 공유 주소장에 표시됩니다. 
    
    > [!IMPORTANT]
    >  외부 연락처를 만들 때 외부 연락처를 만드는 데 필요한 속성(헤더 행의 처음 4개 항목)은 CSV 파일에 채워야 합니다. **ExternalEmailAddress,** **Name,** **FirstName,** **LastName**. 2단계에서 실행한 PowerShell 명령은 이러한 속성의 값을 사용하여 연락처를 생성합니다. 

## <a name="step-2-create-the-external-contacts-with-powershell"></a>2단계: PowerShell을 사용하여 외부 연락처 만들기

다음 단계는 1단계 및 PowerShell에서 만든 CSV 파일을 사용하여 CSV 파일에 나열된 외부 연락처를 대량으로 가져오는 Exchange Online. 
  
1.  커넥트 조직에 대한 PowerShell Exchange Online. 단계별 지침은 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하십시오. PowerShell에 연결할 때 전역 관리자 계정의 사용자 이름과 암호를 Exchange Online 합니다. 
    
2. PowerShell을 Exchange Online 1단계에서 CSV 파일을 저장한 데스크톱 폴더로 이동합니다. 예를 들면 `C:\Users\Administrator\desktop` 입니다.
    
3. 다음 명령을 실행하여 외부 연락처를 만들 수 있습니다.

    ```powershell
    Import-Csv .\ExternalContacts.csv|%{New-MailContact -Name $_.Name -DisplayName $_.Name -ExternalEmailAddress $_.ExternalEmailAddress -FirstName $_.FirstName -LastName $_.LastName}
    ```

    가져오는 연락처 수에 따라 새 연락처를 만드는 데 시간이 걸릴 수 있습니다. 명령 실행이 완료되면 PowerShell에 만들어진 새 연락처의 목록이 표시됩니다. 
    
4. 새 외부 연락처를 보려면 EAC(Exchange 관리 센터)로 이동한  다음 받는 사람 연락처 \> **를 클릭합니다.** 
    
    > [!TIP]
    > EAC에 연결하는 방법에 대한 지침은 에서 Exchange [관리 센터를 Exchange Online.](/exchange/exchange-admin-center) 
  
5. 필요한 경우 새로 **고침을** 클릭하여 목록을 업데이트하고 가져온 외부 연락처를 봐야 합니다. 
    
    가져온 연락처는 공유 주소 Outlook 웹용 Outlook.
    
    > [!NOTE]
    > 사용자 연락처로 Microsoft 365 관리 센터 **연락처를 볼** \> **수 있습니다.** 

## <a name="step-3-add-information-to-the-properties-of-the-external-contacts"></a>3단계: 외부 연락처의 속성에 정보 추가

2단계에서 명령을 실행하면 외부 연락처가 만들어지지만 CSV 파일에 있는 대부분의 셀의 정보인 연락처나 조직 정보는 포함되지 않습니다. 이는 새 외부 연락처를 만들 때 필요한 속성만 채워지기 때문에입니다. CSV 파일에 정보가 모두 채워지는 경우 걱정하지 마세요. 여기에 없는 경우 추가되지 않습니다.
  
1.  커넥트 조직에 대한 PowerShell Exchange Online. 단계별 지침은 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하십시오.
    
2. 1단계에서 CSV 파일을 저장한 데스크톱 폴더로 이동합니다. 예를 들면 `C:\Users\Administrator\desktop` 입니다.
    
3. 다음 두 명령을 실행하여 CSV 파일의 다른 속성을 2단계에서 만든 외부 연락처에 추가합니다.
    
    ```powershell
    $Contacts = Import-CSV .\ExternalContacts.csv
  
    ```

    ```powershell
    $contacts | ForEach {Set-Contact $_.Name -StreetAddress $_.StreetAddress -City $_.City -StateorProvince $_.StateorProvince -PostalCode $_.PostalCode -Phone $_.Phone -MobilePhone $_.MobilePhone -Pager $_.Pager -HomePhone $_.HomePhone -Company $_.Company -Title $_.Title -OtherTelephone $_.OtherTelephone -Department $_.Department -Fax $_.Fax -Initials $_.Initials -Notes  $_.Notes -Office $_.Office -Manager $_.Manager}
    ```

    > [!NOTE]
    > Manager  _매개_ 변수에 문제가 있을 수 있습니다. CSV 파일에 셀이 비어 있는 경우 오류가 발생하고 연락처에 속성 정보가 추가되지 않습니다. 관리자를 지정할 필요가 없는 경우 이전 PowerShell 명령에서  ` -Manager $_.Manager ` 삭제하면 됩니다. 
  
    1단계에서 가져온 수에 따라 연락처를 업데이트하는 데 시간이 걸릴 수 있습니다. 
    
4. 속성이 연락처에 추가 는 확인: 
    
1. Exchange <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">관리 센터에서</a>받는 사람 **연락처로** \> **이동하세요.**
    
2. 연락처를 클릭한 다음 편집 **편집 아이콘을** ![ 클릭합니다.](../media/ebd260e4-3556-4fb0-b0bb-cc489773042c.gif) 를 사용하여 연락처의 속성을 표시합니다. 
    
모두 완료되었습니다. 사용자는 주소장 및 연락처 및 주소 Outlook 추가 정보를 볼 웹용 Outlook.
  
## <a name="add-more-external-contacts"></a>외부 연락처 추가

1~3단계를 반복하여 외부 연락처에 새 외부 연락처를 추가할 Exchange Online. 사용자 또는 회사의 사용자는 새 연락처의 CSV 파일에 새 행을 추가할 수 있습니다. 그런 다음 2단계 및 3단계의 PowerShell 명령을 실행하여 새 연락처에 정보를 만들고 추가할 수 있습니다.
  
> [!NOTE]
> 명령을 실행하여 새 연락처를 만들면 앞에서 만든 연락처가 이미 존재하다는 오류가 발생할 수 있습니다. 그러나 CSV 파일에 추가된 새 연락처가 만들어집니다. 
  
## <a name="hide-external-contacts-from-the-shared-address-book"></a>공유 주소장에서 외부 연락처 숨기기>

일부 회사에서는 외부 연락처만 사용하여 메일 그룹의 구성원으로 추가할 수 있습니다. 이 시나리오에서는 공유 주소 책에서 외부 연락처를 숨길 수 있습니다. 방법은 다음과 같습니다.
  
1.  커넥트 조직에 대한 PowerShell Exchange Online. 단계별 지침은 [Exchange Online PowerShell에 연결](/powershell/exchange/connect-to-exchange-online-powershell)을 참조하십시오.
    
2. 단일 외부 연락처를 숨기기 위해 다음 명령을 실행합니다.
    
    ```powershell
    Set-MailContact <external contact> -HiddenFromAddressListsEnabled $true 
    ```

    예를 들어 공유 주소 책에서 Pilar Pinilla를 숨기기 위해 다음 명령을 실행합니다.

    ```powershell
    Set-MailContact "Pilar Pinilla" -HiddenFromAddressListsEnabled $true
    ```

3. 공유 주소 책에서 모든 외부 연락처를 숨기기 위해 다음 명령을 실행합니다.

    ```powershell
    Get-Contact -ResultSize unlimited -Filter {(RecipientTypeDetails -eq 'MailContact')} | Set-MailContact -HiddenFromAddressListsEnabled $true  
    ```

외부 연락처를 숨기면 외부 연락처가 공유 주소장에 표시되지 않지만 메일 그룹의 구성원으로 추가할 수 있습니다.