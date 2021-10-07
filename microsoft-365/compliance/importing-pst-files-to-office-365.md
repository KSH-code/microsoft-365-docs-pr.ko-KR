---
title: 조직의 PST 파일을 가져오기 개요
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.IngestionHelp
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: ba688e0a-0fcb-4bd7-8e57-2b669564ea84
ms.custom:
- seo-marvel-apr2020
- admindeeplinkMAC
description: Microsoft 365 규정 준수 센터에서 가져오기 서비스를 사용하여 전자 메일 데이터 (PST 파일)를 사용자 사서함에 대량으로 가져오는 방법에 대해 알아보세요.
ms.openlocfilehash: ba757f55e226d436250efa4da3340253dc017be6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190848"
---
# <a name="overview-of-importing-your-organizations-pst-files"></a>조직의 PST 파일을 가져오기 개요

> [!NOTE]
> 이 문서는 관리자를 위해 작성되었습니다. PST 파일을 사서함으로 가져오려고 하나요? [Outlook .pst 파일에서 전자 메일, 연락처 및 일정 가져오기](https://go.microsoft.com/fwlink/p/?LinkID=785075)를 참조하세요.

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 규정 준수 센터</a>에서 가져오기 서비스를 사용하면 PST 파일을 조직의 Exchange Online 사서함으로 신속하게 대량으로 가져올 수 있습니다. Office 365로 PST 파일을 가져올 수 있는 두 가지 방법이 있습니다.

- **네트워크 업로드**![클라우드 업로드](../media/54ab16ee-3822-4551-abef-3d926f4e1c01.png). 네트워크를 통해 PST 파일을 Microsoft 클라우드의 임시 Azure Storage 위치에 업로드합니다. 그런 다음 가져오기 서비스를 사용하여 PST 데이터를 Office 365 조직의 사서함으로 가져옵니다.

- **드라이브 배송**![하드 디스크.](../media/e72b76f3-1f73-4296-b749-c325d95d9ef6.png) - PST 파일을 BitLocker로 암호화된 하드 드라이브에 복사한 다음 하드 드라이브를 Microsoft에 물리적으로 발송합니다. Microsoft가 하드 드라이브를 받으면 데이터 센터 담당자는 Microsoft 클라우드의 임시 Azure Storage에 데이터를 업로드합니다. 그런 다음 가져오기 서비스를 사용하여 데이터를 Office 365 조직의 사서함으로 가져옵니다.

## <a name="step-by-step-instructions"></a>단계별 지침

조직의 PST 파일을 Office 365로 대량으로 가져오는 방법에 대한 자세한 단계별 지침은 다음 항목 중 하나를 참조 하세요.

- [네트워크 업로드를 사용하여 PST 파일을 Office 365로 가져오기](use-network-upload-to-import-pst-files.md)

- [드라이브 발송을 사용하여 PST 파일 가져오기](use-drive-shipping-to-import-pst-files-to-office-365.md)

## <a name="how-importing-pst-files-works"></a>PST 파일을 가져오는 방법

다음은 PST 가져오기 프로세스의 전체적인 그림과 설명입니다. 이 그림은 기본 워크플로를 보여 주며 네트워크 업로드 및 드라이브 배송 방법 간의 차이점을 강조 표시합니다.

![PST 가져오기 프로세스의 워크플로.](../media/76997b69-67d7-433a-a0ca-9389f85a36a1.png)

1. **PST 가져오기 도구 및 키를 개인 Azure Storage 위치로 다운로드** - 첫 번째 단계는 PST 파일을 업로드하거나 하드 드라이브에 복사하는 데 사용되는 도구 및 액세스 키를 다운로드하는 것입니다. 이러한 내용은 Microsoft 365 규정 준수 센터의 **가져오기** 페이지에서 얻게 됩니다. 이 키는 PST 파일을 비공개 보안 Azure Storage 위치에 업로드하는 데 필요한 권한을 가진 (또는 드라이브 배송의 경우 Microsoft 데이터 센터 직원)에게 제공됩니다. 이 액세스 키는 조직에 고유하며 PST 파일이 Microsoft 클라우드에 업로드된 후 PST 파일에 대한 무단 액세스를 방지하는 데 도움이 됩니다. PST 파일을 Microsoft 365로 가져오는 경우 조직에 별도의 Azure 구독을 사용할 필요가 없습니다.

2. **PST 파일 업로드 또는 복사** - 다음 단계는 PST 파일을 가져오기 위해 네트워크 업로드 또는 드라이브 배송을 사용하는지 여부에 따라 달라집니다. 두 경우 모두 이전 단계에서 얻은 도구와 보안 저장소 키를 사용하게 됩니다.

    - **네트워크 업로드:** AzCopy.exe 도구(1단계에서 다운로드)는 PST 파일을 Microsoft 클라우드의 Azure Storage에 업로드하고 저장하는 데 사용됩니다. PST 파일을 업로드 하는 Azure Storage 위치는 조직이 있는 동일한 지역 Microsoft 데이터 센터에 있습니다.

      파일을 업로드하려면 가져오려는 PST 파일이 조직의 파일 공유 또는 파일 서버에 위치해야 합니다.

    - **드라이브 배송:** WAImportExport.exe 도구 (1단계에서 다운로드)는 PST 파일을 하드 드라이브로 복사하는 데 사용됩니다. 이 도구는 BitLocker로 하드 드라이브를 암호화한 다음 PST를 하드 드라이브에 복사합니다. 네트워크 업로드와 마찬가지로 하드 드라이브에 복사하려는 PST 파일은 조직의 파일 공유 또는 파일 서버에 위치해야 합니다.

3. **PST 가져오기 매핑 파일 만들기** - PST 파일을 Azure Storage 위치에 업로드하거나 하드 드라이브에 복사한 후의 다음 단계는 가져온 PST파일이 위치하게 될 사용자 사서함을 지정하는 쉼표로 구분된 값 (CSV) 파일을 만드는 것입니다 (PST 파일은 사용자의 기본 사서함이나 보관 사서함으로 가져올 수 있습니다). [PST 가져오기 매핑 파일의 복사본 다운로드](https://go.microsoft.com/fwlink/p/?LinkId=544717). Office 365 가져오기 서비스는 이 정보를 사용하여 PST 파일을 가져옵니다.

4. **PST 가져오기 작업 만들기** - 다음 단계는 Microsoft 365 규정 준수 센터의 **PST 파일 가져오기** 페이지에서 PST 가져오기 작업을 만들고 이전 단계에서 만든 PST 가져오기 매핑 파일을 제출하는 것입니다. 네트워크 업로드의 경우 (PST 파일이 Azure에 업로드 되었기 때문에) Microsoft 365는 PST 파일의 데이터를 분석한 다음 PST 가져오기 매핑 파일에 지정된 사서함으로 실제로 가져올 데이터를 제어하는 필터를 설정할 수 있는 기회를 제공합니다.

    드라이브 배송의 경우, 이 과정에서 몇 가지 다른 상황이 발생합니다.

    - 하드 드라이브를 실제로 Microsoft 데이터 센터로 발송하세요 (가져오기 작업을 만들 때 Microsoft 데이터 센터의 주소가 표시됨).

    - Microsoft가 하드 드라이브를 받으면 데이터 센터 담당자는 하드 드라이브의 PST 파일을 조직의 Azure Storage 위치로 업로드합니다. 앞서 설명한 것처럼 PST 파일은 조직이 있는 동일한 지역 Microsoft 데이터 센터에 있는 Azure Storage 위치에 업로드됩니다.

      > [!NOTE]
      > 하드 드라이브의 PST 파일은 Microsoft에서 하드 드라이브를 받은 후 7 ~ 10 영업일 이내에 Azure에 업로드 됩니다.

      네트워크 업로드 프로세스와 마찬가지로 Microsoft 365는 PST 파일의 데이터를 분석한 다음 PST 가져오기 매핑 파일에 지정된 사서함으로 실제로 가져올 데이터를 제어하는 필터를 설정할 수 있는 기회를 제공합니다.

    - Microsoft는 하드 드라이브를 다시 사용자에게 발송합니다.

5. **사서함으로 가져올 PST 데이터 필터링** - 가져오기 작업을 만든 후 (또한 드라이브 배송 작업의 PST 파일이 Azure Storage 위치로 업로드된 후) Microsoft 365에서 PST 파일의 데이터를 PST 파일에 포함된 다양한 메시지 유형과 항목의 보존 기간을 식별하는 방법으로 안전하고 꼼꼼하게 분석합니다. 분석이 완료되고 데이터를 가져올 준비가 되면 PST 파일에 포함된 모든 데이터를 가져오거나 가져올 데이터를 제어하는 필터를 설정하여 가져온 데이터를 트리밍할 수 있습니다.

6. **PST 가져오기 작업 시작하기** - 가져오기 작업이 시작되면 Microsoft 365는 PST 가져오기 매핑 파일의 정보를 사용하여 Azure Storage 위치의 PST 파일을 사용자 사서함으로 가져옵니다. 가져오기 작업에 대한 상태 정보(가져오는 각 PST 파일에 대한 정보 포함)는 Microsoft 365 규정 준수 센터의 **PST 파일 가져오기** 페이지에 표시됩니다. 가져오기 작업이 완료되면 해당 작업의 상태가 **완료** 로 설정됩니다.

## <a name="why-import-email-data-to-microsoft-365"></a>Microsoft 365로 전자 메일 데이터를 가져오는 이유는 무엇인가요?

- 조직에서 보관하는 메시징 데이터를 Microsoft 365로 가져오는 좋은 방법입니다.

- [지능형 가져오기](filter-data-when-importing-pst-files.md) 기능을 사용하여 실제로 대상 사서함으로 가져온 PST 파일의 항목을 필터링할 수 있습니다. 이렇게하면 가져올 데이터를 제어하는 필터를 설정하여 가져온 데이터를 트리밍할 수 있습니다.

- Microsoft 365로 전자 메일 데이터를 가져와 다음을 통해 조직의 준수 요구 사항을 해결할 수 있습니다.

  - [보관 사서함](enable-archive-mailboxes.md) 및 [자동 확장 보관](autoexpanding-archiving.md)을 활성화하여 사용자에게 추가 사서함 저장 공간을 제공합니다.

  - [소송 증거 유지](./create-a-litigation-hold.md)에 사서함을 두어 내용을 보존합니다.

  - [콘텐츠 검색 도구](content-search.md)를 사용하여 사서함 콘텐츠를 검색합니다.

  - [eDiscovery 사례](./get-started-core-ediscovery.md)를 사용하여 조직의 법적 조사를 관리합니다.

  - Microsoft 365 규정 준수 센터의 [보존 정책](retention.md)을 사용하여 사서함 콘텐츠의 보존 기간을 제어하고, 보존 기간이 만료되면 콘텐츠를 삭제합니다.

  - [커뮤니케이션 규정 준수 정책](communication-compliance.md)을 사용하여 메시지 표준을 준수하는지 확인하고 분류 유형을 추가합니다.

- Microsoft 365로 데이터를 가져오면 데이터 손실을 막을 수 있습니다. Microsoft 365로 가져온 전자 메일 데이터는 Exchange Online의 고가용성 기능을 상속합니다.

- 전자 메일 데이터는 클라우드에 저장되므로 모든 장치에서 사용할 수 있습니다.

## <a name="importing-sharepoint-data-to-microsoft-365"></a>Microsoft 365로 SharePoint 데이터 가져오기

조직에서 SharePoint 사이트 및 OneDrive 계정으로 파일 및 문서를 가져올 수도 있습니다. 자세한 내용은 다음 문서를 참조하십시오.

- [SharePoint Online으로 마이그레이션](/sharepointmigration/migrate-to-sharepoint-online)

- [SharePoint 마이그레이션 도구 소개](/sharepointmigration/introducing-the-sharepoint-migration-tool)

- [PowerShell을 사용하여 SharePoint Online으로 마이그레이션](/sharepointmigration/overview-spmt-ps-cmdlets)

- [Azure Data Box를 사용하여 파일 공유 콘텐츠를 SharePoint Online으로 마이그레이션](/sharepointmigration/how-to-migrate-file-share-content-to-spo-using-azuredatabox)

## <a name="frequently-asked-questions-about-importing-pst-files"></a>PST 파일을 가져오는 방법에 대한 자주 묻는 질문과 대답

다음은 Microsoft 365 가져오기 서비스를 사용하여 PST 파일을 Office 365 사서함에 대량으로 가져오는 방법에 대한 몇 가지 자주 묻는 질문과 대답입니다.

- [네트워크 업로드를 사용하여 PST 파일 가져오기](#using-network-upload-to-import-pst-files)

- [드라이브 배송을 사용하여 PST 파일 가져오기](#using-drive-shipping-to-import-pst-files)

### <a name="using-network-upload-to-import-pst-files"></a>네트워크 업로드를 사용하여 PST 파일 가져오기

#### <a name="what-permissions-are-required-to-create-import-jobs-in-the-office-365-import-service-using-network-upload"></a>네트워크 업로드를 사용하여 Office 365 가져오기 서비스에서 가져오기 작업을 만드는 데 필요한 권한은 무엇입니까?

PST 파일을 Microsoft 365 사서함으로 가져오려면 Exchange Online의 사서함 가져오기 내보내기 역할을 할당받아야 합니다. 기본적으로 이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다. 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다. 또는 새 역할 그룹을 만들고, 사서함 가져오기 내보내기 역할을 할당한 다음 구성원으로 자신이나 다른 사용자를 추가할 수 있습니다. 자세한 내용은 [Exchange Online에서 역할 그룹 관리](/Exchange/permissions-exo/role-groups)의 "역할 그룹에 역할 추가" 또는 "역할 그룹 만들기" 섹션을 참조하세요.

또한 Microsoft 365 규정 준수 센터에서 가져오기 작업을 만들려면 다음 중 하나를 충족해야 합니다.

- Exchange Online에서 전자 메일 받는 사람 역할을 할당받아야 합니다. 이 역할은 조직 관리 및 받는 사람 관리 역할 그룹에 기본값으로 할당됩니다.

    또는

- 조직의 전역 관리자여야 합니다.

> [!TIP]
> Exchange Online에서 PST 파일을 Office 365로 가져오기 위한 새로운 역할 그룹을 만드는 것이 좋습니다. PST 파일을 가져오는 데 필요한 최소 수준의 권한만 할당하려면 새 역할 그룹에 사서함 가져오기/내보내기 역할 및 메일 받는 사람 역할을 할당하고 구성원을 추가합니다.

#### <a name="where-is-network-upload-available"></a>네트워크 업로드는 어디에서 사용할 수 있나요?

네트워크 업로드는 현재 다음 지역에서 사용할 수 있습니다. 미국, 캐나다, 브라질, 영국, 프랑스, 독일, 스위스, 노르웨이, 유럽, 인도, 동아시아, 동남아시아, 일본, 대한민국, 호주, 아랍에미리트(UAE)입니다. 네트워크 업로드는 더 많은 지역에서 곧 사용할 수 있습니다.

#### <a name="what-is-the-pricing-for-importing-pst-files-by-using-network-upload"></a>What is the pricing for importing PST files by using network upload?

Using network upload to import PST files is free.

이는 또한 PST 파일이 Azure Storage 영역에서 삭제된 후 [Microsoft 365 관리 센터](https://go.microsoft.com/fwlink/p/?linkid=2024339)의 완료된 가져오기 작업에 대한 파일 목록에 더 이상 표시되지 않음을 의미합니다. 가져오기 작업이 **Office 365로 데이터 가져오기** 페이지에 계속 나열될 수 있지만 이전 가져오기 작업의 세부 정보를 볼 때 PST 파일 목록이 비어 있을 수 있습니다.

#### <a name="what-version-of-the-pst-file-format-is-supported-for-importing-to-office-365"></a>What version of the PST file format is supported for importing to Office 365?

PST 파일 형식의 버전은 두 가지로, ANSI와 유니코드입니다. 유니코드 PST 파일 형식을 사용하는 파일을 가져오는 것이 좋습니다. 하지만 DBCS(더블바이트 문자 집합)를 사용하는 언어를 위한 파일 형식 등 ANSI PST를 사용하는 파일도 Office365로 가져올 수 있습니다. ANSI PST 파일 가져오기에 대한 자세한 내용은 [네트워크 업로드를 사용하여 PST 파일을 Office 365로 가져오기](./use-network-upload-to-import-pst-files.md)의 4단계를 참조하세요.

또한 Outlook 2007 이상 버전의 PST 파일도 Office 365로 가져올 수 있습니다.

#### <a name="after-i-upload-my-pst-files-to-the-azure-storage-area-how-long-are-they-kept-in-azure-before-theyre-deleted"></a>Azure Storage 영역으로 내 PST 파일을 업로드한 후 삭제되기까지 Azure에서 얼마나 보관되나요?

네트워크 업로드 방법을 사용하여 PST 파일을 가져오는 경우 Azure BLOB 컨테이너로 해당 파일을 업로드하는 것입니다.`ingestiondata` Microsoft 365 규정 준수 센터에서 **PST 파일 가져오기** 페이지의 가져오기 작업이 진행 중이 아니라면 Azure의 `ingestiondata` 컨테이너에 포함된 모든 PST 파일이 Microsoft 365 규정 준수 센터에서 가장 최근에 가져오기 작업이 생성된 날짜로부터 30일 후에 삭제됩니다. 즉, PST 파일을 Azure로 업로드한 후 30일 이내에 Microsoft 365 규정 준수 센터(네트워크 업로드 지침의 5단계에 설명됨)에 새 가져오기 작업을 만들어야 합니다.

이는 또한 PST 파일이 Azure Storage 영역에서 삭제된 후 Microsoft 365 규정 준수 센터의 완료된 가져오기 작업에 대한 파일 목록에 더 이상 표시되지 않음을 의미합니다. 가져오기 작업이 Microsoft 365 준수 센터의 **PST 파일 가져오기 페이지** 에 계속 나열될 수 있지만 이전 가져오기 작업의 세부 정보를 볼 때 PST 파일 목록이 비어 있을 수 있습니다.

#### <a name="how-long-does-it-take-to-import-a-pst-file-to-a-mailbox-using-network-upload"></a>네트워크 업로드를 사용하여 PST 파일을 사서함으로 가져오는 데 얼마나 걸리나요?

트워크 용량에 따라 달라지지만 1TB(테라바이트)의 데이터를 조직의 Azure Storage 영역에 업로드하는 데 일반적으로 몇 시간이 걸립니다. PST 파일을 Azure Storage 영역으로 복사한 후 약 하루당 24GB 속도로 PST 파일을 Microsoft 365 사서함으로 가져올 수 있습니다<sup>\*</sup>. 이 속도가 요구 사항을 충족하지 않는 경우 전자 메일 데이터를 Office 365로 가져오는 다른 방법을 고려할 수 있습니다. 자세한 내용은 [Office 365로 여러 전자 메일 계정을 마이그레이션하는 방법](/Exchange/mailbox-migration/mailbox-migration)을 참조하세요.

<sup>\*</sup>이 속도는 보장되지 않습니다. 서버 워크로드 및 일시적인 성능 문제로 이 속도가 저하될 수 있습니다.

다른 PST 파일을 다른 대상 사서함으로 가져오는 경우 가져오기 프로세스가 동시에 수행됩니다. 즉, 각 PST/사서함 쌍을 동시에 가져올 수 있습니다. 여러 PST 파일을 동일한 사서함으로 가져오는 경우 동시에 가져오지 않고 순차적으로(한 번에 하나씩) 가져옵니다.

#### <a name="how-does-the-pst-import-process-handle-duplicate-email-items"></a>PST 가져오기 프로세스는 중복 전자 메일 항목을 어떻게 처리합니까?

PST 가져오기 프로세스는 중복 항목을 확인하고 대상 사서함 또는 대상 아카이브의 대상 폴더에 일치하는 항목이 있는 경우 PST 파일에서 사서함 또는 아카이브로 항목을 복사하지 않습니다. 동일한 PST 파일을 다시 가져오고 이전 가져오기 작업에서 지정한 폴더와 다른 대상 폴더(PST 가져오기 매핑 파일의 TargetRootFolder 속성을 사용하여)를 지정하면 PST 파일의 모든 항목을 다시 가져옵니다.

#### <a name="is-there-a-message-size-limit-when-importing-pst-files-using-network-upload"></a>네트워크 업로드를 사용하여 PST 파일을 가져올 때 메시지 크기가 제한되나요?

예. PST 파일이 150MB보다 큰 사서함을 포함한 경우 가져오기 프로세스 동안 항목을 가져오지 않고 건너뜁니다. 150MB보다 큰 항목은 Exchange Online의 메시지 크기 제한이 150MB이기 때문에 가져오지 않습니다. 자세한 내용은 [Exchange Online의 메시지 제한](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits)을 참조하세요.

#### <a name="are-message-properties-such-as-when-the-message-was-sent-or-received-the-list-of-recipients-and-other-properties-preserved-when-pst-files-are-imported-to-a-microsoft-365-mailbox-using-network-upload"></a>네트워크 업로드를 사용하여 PST 파일을 Microsoft 365 사서함으로 가져올 때 메시지를 보내거나 받은 시간, 받는 사람의 목록, 기타 속성 등 메시지 속성이 보존되나요?

예. 가져오기 프로세스 중에는 원본 메시지 메타데이터가 변경되지 않습니다.

#### <a name="is-there-a-limit-to-the-number-of-levels-in-a-folder-hierarchy-for-a-pst-file-that-i-want-to-import-to-a-mailbox-using-network-upload"></a>네트워크 업로드를 사용하여 사서함으로 가져오려는 PST 파일의 폴더 계층 구조에서 레벨 수에 제한이 있나요?

예. 300개 이상의 중첩 폴더 레벨이 있는 PST 파일을 가져올 수 없습니다.

#### <a name="can-i-use-network-upload-to-import-pst-files-to-an-inactive-mailbox-in-office-365"></a>Can I use network upload to import PST files to an inactive mailbox in Office 365?

Yes, this capability is now available.

#### <a name="can-i-use-network-upload-to-import-pst-files-to-an-online-archive-mailbox-in-an-exchange-hybrid-deployment"></a>Can I use network upload to import PST files to an online archive mailbox in an Exchange hybrid deployment?

Yes, this capability is now available.

#### <a name="can-i-use-network-upload-to-import-pst-files-to-public-folders-in-exchange-online"></a>Exchange Online의 공용 폴더로 PST 파일 가져오는데 네트워크 업로드를 사용할 수 있나요?

아니요, 공용 폴더에 PST 파일을 가져올 수 없습니다.

### <a name="using-drive-shipping-to-import-pst-files"></a>드라이브 배송을 사용하여 PST 파일 가져오기

#### <a name="what-permissions-are-required-to-create-import-jobs-in-the-office-365-import-service-using-drive-shipping"></a>드라이브 이동을 사용하여 Office 365 가져오기 서비스에서 가져오기 작업을 만드는 데 필요한 권한은 무엇입니까?

PST 파일을 Microsoft 365 사서함으로 가져오려면 사서함 가져오기 내보내기 역할을 할당받아야 합니다. 기본적으로 이 역할은 Exchange Online의 어떤 역할 그룹에도 할당되지 않습니다. 조직 관리 역할 그룹에 사서함 가져오기 내보내기 역할을 추가할 수 있습니다. 또는 새 역할 그룹을 만들고, 사서함 가져오기 내보내기 역할을 할당한 다음 구성원으로 자신이나 다른 사용자를 추가할 수 있습니다. 자세한 내용은 [Exchange Online에서 역할 그룹 관리](/Exchange/permissions-exo/role-groups)의 "역할 그룹에 역할 추가" 또는 "역할 그룹 만들기" 섹션을 참조하세요.

또한 Microsoft 365 규정 준수 센터에서 가져오기 작업을 만들려면 다음 중 하나를 충족해야 합니다.

- Exchange Online에서 전자 메일 받는 사람 역할을 할당받아야 합니다. 이 역할은 조직 관리 및 받는 사람 관리 역할 그룹에 기본값으로 할당됩니다.

    또는

- 조직의 전역 관리자여야 합니다.

> [!TIP]
> Exchange Online에서 PST 파일을 Office 365로 가져오기 위한 새로운 역할 그룹을 만드는 것이 좋습니다. PST 파일을 가져오는 데 필요한 최소 수준의 권한만 할당하려면 새 역할 그룹에 사서함 가져오기/내보내기 역할 및 메일 받는 사람 역할을 할당하고 구성원을 추가합니다.

#### <a name="where-is-drive-shipping-available"></a>드라이브 배송을 사용할 수 있는 지역은 어디인가요?

현재 드라이브 배송은 미국, 캐나다, 브라질, 영국, 유럽, 인도, 동아시아, 동남 아시아, 일본, 대한민국, 오스트레일리아 및 남아프리카에서 사용할 수 있습니다. 드라이브 배송을 사용할 수 있는 지역이 곧 더 많아질 예정입니다.

> [!NOTE]
> 현재 독일 및 스위스에서는 PST 파일을 가져오기 위한 드라이브 배송을 사용할 수 없습니다. 이러한 국가에서 드라이브 배송이 가능한 경우 이 FAQ가 업데이트됩니다.

#### <a name="what-commercial-licensing-agreements-support-drive-shipping"></a>어떤 상업용 사용권 계약을 통해 드라이브 배송을 사용할 수 있나요?

PST 파일을 Microsoft 365로 가져오기 위한 드라이브 배송은 Microsoft EA(Enterprise Agreement)를 통해 가능합니다. MPSA(Microsoft 제품 및 서비스 계약)를 통해서는 드라이브 배송이 가능하지 않습니다.

#### <a name="what-is-the-pricing-for-using-drive-shipping-to-import-pst-files-to-microsoft-365"></a>파일을 Microsoft 365로 가져오기 위해 드라이브 배송을 사용하는 경우 그 가격은 얼마인가요?

Microsoft 365 사서함으로 PST 파일을 가져오기 위해 드라이브 배송을 사용하는 비용은 1GB의 데이터당 2,000원입니다. 예를 들어 1,000GB(1TB)의 PST 파일이 포함된 하드 드라이브를 배송하는 경우 비용은 2,000,000원입니다. 파트너와 협력하여 가져오기 요금을 지불할 수 있습니다. 파트너를 찾는 방법에 대한 내용은 [Microsoft 365 파트너 또는 재판매인 찾기](../admin/manage/find-your-partner-or-reseller.md)를 참조하세요.

#### <a name="what-kind-of-hard-drives-are-supported-for-drive-shipping"></a>드라이브 배송이 가능한 하드 드라이브는 어떤 종류인가요?

Office 365 가져오기 서비스에서는 2.5인치 SSD(반도체 드라이브)나 2.5인치 또는 3.5인치 SATA II/III 내장 하드 드라이브를 지원합니다. 최대 10TB의 하드 드라이브를 사용할 수 있습니다. 가져오기 작업의 경우에는 하드 드라이브의 첫 번째 데이터 볼륨만 처리됩니다. 데이터 볼륨은 NTFS 형식으로 포맷되어야 합니다. 하드 드라이브에 데이터를 복사할 때는 2.5인치 SSD나 2.5인치 또는 3.5인치 SATA II/III 커넥터를 사용하여 직접 연결하거나 외장 2.5인치 SSD나 2.5인치 또는 3.5인치 SATA II/III USB 어댑터를 사용하여 외장으로 연결할 수 있습니다.

> [!IMPORTANT]
> USB 어댑터가 내장되어 함께 제공되는 외장 하드 드라이브는 Office 365 가져오기 서비스에서 지원하지 않습니다. 또한, 외장 하드 드라이브 케이스에 들어 있는 디스크는 사용할 수 없습니다. 외장 하드 드라이브는 발송하지 마시기 바랍니다.

#### <a name="how-many-hard-drives-can-i-ship-for-a-single-import-job"></a>How many hard drives can I ship for a single import job?

You can ship a maximum of 10 hard drives for a single import job.

#### <a name="after-i-ship-my-hard-drive-how-long-does-it-take-to-get-to-the-microsoft-datacenter"></a>하드 드라이브를 배송한 후 Microsoft 데이터 센터에 가져오는 데 얼마나 걸리나요?

해당 기간은 Microsoft 데이터 센터에 대한 근접성, 하드 드라이브를 배송하는 데 사용한 배송 옵션 종류(예: 익일 배송, 2일 배송 또는 육로 배송) 등의 몇 가지 요인에 따라 다릅니다. 대부분의 운송업체에서, 추적 번호를 사용하여 배송 상태를 추적할 수 있습니다.

#### <a name="after-my-hard-drive-arrives-at-the-microsoft-datacenter-how-long-does-it-take-to-upload-my-pst-files-to-azure"></a>하드 드라이브가 Microsoft 데이터 센터에 도착하면 내 PST 파일을 Azure에 업로드하는 데 얼마나 걸리나요?

Microsoft 데이터 센터에서 하드 드라이브를 받은 후 PST 파일을 조직의 Azure Storage 위치에 업로드하는 데 영업일 기준 7~10일이 소요됩니다. PST 파일은 `ingestiondata`(이)라는 Azure Blob 컨테이너에 업로드됩니다.

#### <a name="how-long-does-it-take-to-import-a-pst-file-to-a-mailbox-using-drive-shipping"></a>드라이브 이동을 사용하여 PST 파일을 사서함으로 가져오는 데 얼마나 걸리나요?

PST 파일이 Azure Storage 영역에 업로드되면 Microsoft 365에서 PST 파일의 데이터를 안전한 방법으로 분석하여 항목 경과 시간과 PST 파일에 포함된 다양한 메시지 유형을 식별합니다. 분석이 완료되면 PST 파일의 모든 데이터를 가져오거나 필터를 설정하여 가져온 데이터를 제어할 수 있는 옵션이 나타납니다. 가져오기 작업을 시작하면 하루당 최소 24GB의 속도로 PST 파일을 Microsoft 365 사서함으로 가져옵니다. 이 속도가 요구 사항을 충족하지 않는 경우 전자 메일 데이터를 Microsoft 365로 가져오는 다른 방법을 고려할 수 있습니다. 자세한 내용은 [Microsoft 365로 여러 전자 메일 계정을 마이그레이션하는 방법](/Exchange/mailbox-migration/mailbox-migration)을 참조하세요.

다른 PST 파일을 다른 대상 사서함으로 가져오는 경우 가져오기 프로세스가 동시에 수행됩니다. 즉, 각 PST/사서함 쌍을 동시에 가져올 수 있습니다. 여러 PST 파일을 동일한 사서함으로 가져오는 경우 동시에 가져오지 않고 순차적으로(한 번에 하나씩) 가져옵니다.

#### <a name="after-microsoft-uploads-my-pst-files-to-azure-how-long-are-they-kept-in-azure-before-theyre-deleted"></a>Microsoft에서 Azure에 내 PST 파일을 업로드한 후 삭제되기까지 Azure에서 얼마나 보관되나요?

조직의 Azure Storage 위치(`ingestiondata`라고 하는 Blob 컨테이너)에 있는 모든 PST 파일은 Microsoft 365 규정 준수 센터에서 **PST 파일 가져오기** 페이지의 가장 최근 가져오기 작업이 만들어지고 30일 후에 삭제됩니다.

이는 또한 PST 파일이 Azure Storage 영역에서 삭제된 후 Microsoft 365 규정 준수 센터의 완료된 가져오기 작업에 대한 파일 목록에 더 이상 표시되지 않음을 의미합니다. 가져오기 작업이 Microsoft 365 준수 센터의 **PST 파일 가져오기 페이지** 에 계속 나열될 수 있지만 이전 가져오기 작업의 세부 정보를 볼 때 PST 파일 목록이 비어 있을 수 있습니다.

#### <a name="what-version-of-the-pst-file-format-is-supported-for-importing-to-microsoft-365"></a>Microsoft 365로 가져올 수 있는 PST 파일 형식의 버전은 어떻게 되나요?

PST 파일 형식의 버전은 두 가지로, ANSI와 유니코드입니다. 유니코드 PST 파일 형식을 사용하는 파일을 가져오는 것이 좋습니다. 하지만 DBCS(더블바이트 문자 집합)를 사용하는 언어를 위한 파일 형식 등 ANSI PST를 사용하는 파일도 Microsoft 365로 가져올 수 있습니다. ANSI PST 파일 가져오기에 대한 자세한 내용은 [드라이브 배송을 사용하여 조직 PST 파일을 Microsoft 365로 가져오기](use-drive-shipping-to-import-pst-files-to-office-365.md#step-3-create-the-pst-import-mapping-file)의 3단계를 참조하세요.

또한 Outlook 2007 이상 버전의 PST 파일도 Microsoft 365로 가져올 수 있습니다.

#### <a name="is-there-a-message-size-limit-when-importing-pst-files-using-drive-shipping"></a>드라이브 이동을 사용하여 PST 파일을 가져올 때 메시지 크기가 제한되나요?

예. PST 파일이 150MB보다 큰 사서함을 포함한 경우 가져오기 프로세스 동안 항목을 가져오지 않고 건너뜁니다. 150MB보다 큰 항목은 Exchange Online의 메시지 크기 제한이 150MB이기 때문에 가져오지 않습니다. 자세한 내용은 [Exchange Online의 메시지 제한](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#message-limits)을 참조하세요.

  **PST 가져오기 프로세스는 중복 전자 메일 항목을 어떻게 처리합니까?

PST 가져오기 프로세스는 중복 항목을 확인하고 대상 사서함 또는 대상 아카이브의 대상 폴더에 일치하는 항목이 있는 경우 PST 파일에서 사서함 또는 아카이브로 항목을 복사하지 않습니다. 동일한 PST 파일을 다시 가져오고 이전 가져오기 작업에서 지정한 폴더와 다른 대상 폴더(PST 가져오기 매핑 파일의 TargetRootFolder 속성을 사용하여)를 지정하면 PST 파일의 모든 항목을 다시 가져옵니다.

#### <a name="are-message-properties-such-as-when-the-message-was-sent-or-received-the-list-of-recipients-and-other-properties-preserved-when-pst-files-are-imported-to-a-microsoft-365-mailbox-using-drive-shipping"></a>드라이브 이동을 사용하여 PST 파일을 Microsoft 365 사서함으로 가져올 때 메시지를 보내거나 받은 시간, 받는 사람의 목록, 기타 속성 등 메시지 속성이 보존되나요?

예. 가져오기 프로세스 중에 원본 메시지 메타데이터가 변경되지 않음

#### <a name="is-there-a-limit-to-the-number-of-levels-in-a-folder-hierarchy-for-a-pst-file-that-i-want-to-import-to-a-mailbox-using-drive-shipping"></a>드라이브 이동을 사용하여 사서함으로 가져오려는 PST 파일의 폴더 계층 구조에서 레벨 수에 제한이 있나요?

예. 300개 이상의 중첩 폴더 레벨이 있는 PST 파일을 가져올 수 없습니다.

#### <a name="can-i-use-drive-shipping-to-import-pst-files-to-an-inactive-mailbox-in-microsoft-365"></a>Microsoft 365의 비활성 사서함으로 PST 파일을 가져오기 위해 드라이브 배송을 사용할 수 있나요?

Yes, this capability is now available.

#### <a name="can-i-use-drive-shipping-to-import-pst-files-to-an-online-archive-mailbox-in-an-exchange-hybrid-deployment"></a>Can I use drive shipping to import PST files to an online archive mailbox in an Exchange hybrid deployment?

Yes, this capability is now available.

#### <a name="can-i-use-drive-shipping-to-import-pst-files-to-public-folders-in-exchange-online"></a>Exchange Online의 공용 폴더로 PST 파일을 가져오는데 드라이브 배송을 사용할 수 있나요?

아니요, 공용 폴더에 PST 파일을 가져올 수 없습니다.

#### <a name="can-microsoft-wipe-my-hard-drive-before-they-ship-it-back-to-me"></a>Microsoft에서 나에게 다시 배송하기 전에 내 하드 드라이브를 초기화할 수 있나요?

No, Microsoft can't wipe hard drives before shipping them back to customers. Hard drives are returned to you in the same state they were in when they were received by Microsoft.

#### <a name="can-microsoft-shred-my-hard-drive-instead-of-shipping-it-back-to-me"></a>Can Microsoft shred my hard drive instead of shipping it back to me?

No, Microsoft can't destroy your hard drive. Hard drives are returned to you in the same state they were in when they were received by Microsoft.

#### <a name="what-courier-services-are-supported-for-return-shipping"></a>What courier services are supported for return shipping?

If you're a customer in the United States or Europe, Microsoft uses FedEx to return your hard drive. For all other regions, Microsoft uses DHL.

#### <a name="what-are-the-return-shipping-costs"></a>What are the return shipping costs?

Return shipping costs vary, depending on your proximity to the Microsoft data center that you shipped your hard drive to. Microsoft will bill your FedEx or DHL account to return your hard drive. The cost of return shipping is your responsibility.

#### <a name="can-i-use-a-custom-courier-shipping-service-such-as-fedex-custom-shipping-to-ship-my-hard-drive-to-microsoft"></a>Can I use a custom courier shipping service, such as FedEx Custom Shipping, to ship my hard drive to Microsoft?

예.

#### <a name="if-i-have-to-ship-my-hard-drive-to-another-country-is-there-anything-i-need-to-do"></a>If I have to ship my hard drive to another country, is there anything I need to do?

Microsoft에 배송하는 하드 드라이브가 국경을 통과해야 하는 경우도 있습니다. 이 경우 해당 법률에 따라 하드 드라이브와 해당 드라이브에 포함된 데이터를 수입 및/또는 수출 할 책임이 있습니다. 하드 드라이브를 배송하기 전에 관리자에게 문의하여 드라이브 및 데이터가 지정된 Microsoft 데이터 센터로 정상적으로 배송될 수 있는지 확인합니다. 이렇게 하면 적시에 Microsoft로 도착할 수 있습니다.
