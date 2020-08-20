---
title: Advanced eDiscovery의 문서 메타데이터 필드
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
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 이 문서에서는 Microsoft 365의 Advanced eDiscovery에 있는 사례에 있는 검토 집합의 문서에 대한 메타데이터 필드를 정의합니다.
ms.openlocfilehash: 69b22155f209f155aa0b311f67f3e69841093003
ms.sourcegitcommit: 167c05cc6a776f62f0a0c2de5f3ffeb68c4a27ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "46814390"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Advanced eDiscovery의 문서 메타데이터 필드

다음 표에는 Advanced eDiscovery의 사례에서 검토 집합의 문서에 대한 메타데이터 필드가 나와 있습니다. 테이블에서는 다음과 같은 정보를 제공합니다.

- **필드 이름** **및 표시 필드 이름:** 리뷰 집합에서 선택된 문서의 파일 메타데이터를 볼 때 표시되는 필드 이름 및 메타데이터 필드이름 일부 메타데이터 필드는 문서의 파일 메타데이터를 볼 때 포함되지 않습니다. 이러한 필드에는 별표(*)가 강조 표시됩니다.

- **검색 가능한 필드 이름:** 검토 집합 쿼리를 실행할 때 검색할 수 있는 속성의 [이름입니다.](review-set-search.md) 빈 셀은 검토 집합 쿼리에서 필드를 검색할 수 없습니다.

- **내보낸 필드 이름:** 문서를 내보낼 때 포함되는 메타데이터 필드의 이름입니다.  빈 셀은 필드가 내보낸 메타데이터에 포함되지 않음을 의미합니다.

- **설명:** 메타데이터 필드에 대한 설명입니다.

> [!NOTE]
> 검토 **집합 검색의** 키워드 [필드에는](https://docs.microsoft.com/microsoft-365/compliance/review-set-search) KQL(키워드 쿼리 언어)을 사용합니다. 검색 가능한 필드 이름 열에 **나열된 필드는** **Keywords** 사용자가 쿼리 작성기를 사용하지 않고도 복잡한 쿼리를 형성하기 위해 검토 집합 검색의 키워드 필드에서 사용할 수 있습니다. KQL에 대한 자세한 내용은 키워드 쿼리 [언어 구문 참조를 참조하세요.](https://go.microsoft.com/fwlink/?LinkId=269603)

|**필드 이름** 및 **표시 필드 이름**|**검색 가능한 필드 이름**|**내보낸 필드 이름**|**설명**|
|:-----|:-----|:-----|:-----|
|첨부 파일 콘텐츠 ID|AttachmentContentId||항목의 첨부 파일 콘텐츠 ID입니다.|
|첨부 파일 이름|AttachmentNames|Attachment_Names|첨부 파일 이름 목록입니다.|
|비밀 유지 권한 점수|AttorneyClientPrivilegeScore||비밀 유지 권한 모델의 콘텐츠 점수입니다.|
|만든 이|만든 이|Doc_authors|문서 메타데이터를 작성합니다.|
|BCC|Bcc|Email_bcc|메시지 유형에 대한 참조 필드입니다. Format은 **DisplayName입니다. \<SMTPAddress> **|
|CC|참조|Email_cc|메시지 유형의 참조 필드입니다. Format은 **DisplayName입니다. \<SMTPAddress> **|
|규정 준수 레이블|ComplianceLabels|Compliance_labels|[Retention labels](retention.md) Office 365의 콘텐츠에 적용되는 보존 레이블|
|복합 경로|CompoundPath|Compound_path|항목의 원본을 설명하는 사용자가 읽을 수 있는 경로입니다.|
|콘텐츠*|콘텐츠||항목에서 추출된 텍스트입니다.|
|대화 본문|대화 본문||항목의 대화 본문입니다.|
|대화 주제|대화 주제||항목의 대화 주제입니다.|
|대화 ID|ConversationId|Conversation_ID|메시지의 대화 ID입니다.|
|대화 인덱스/Conversation Index||Conversation_index|메시지에서 대화 색인입니다.|
|대화 Pdf 시간|ConversationPdfTime||대화의 PDF 버전을 만든 날짜입니다.|
|대화 상산 버스 시간|ConversationRedactionBurnTime||채팅을 위한 대화의 PDF 버전이 만들어진 날짜입니다.|
|만든 문서 날짜|CreatedTime|Doc_date_created|문서 메타데이터에서 날짜를 만듭니다.|
|보토어|보토어|보토어|항목이 연결된 보유자의 이름입니다.|
|날짜|날짜|날짜|Date는 파일 형식에 종속되는 계산 필드입니다.<br /><br />전자 메일: 보낸 날짜<br />전자 메일 첨부 파일: 문서를 마지막으로 수정한 날짜입니다. 사용할 수 없는 경우 부모는 보낸 날짜입니다.<br />포함된 문서: 문서의 마지막으로 수정한 날짜 사용할 수 없는 경우 부모의 마지막으로 수정한 날짜<br />SPO 문서(최신 첨부 파일 포함): SharePoint 마지막으로 수정한 날짜 없는 경우 문서를 마지막으로 수정한 날짜<br />비 Office 365 문서: 마지막으로 수정한 날짜<br />모임: 모임 시작 날짜<br />VoiceMail: Sent date<br />IM: 전송 날짜|
|기타 경로|Dedupedcompoundpath|Deduped_compound_path|정확하게 중복되는 문서의 복합 경로 목록(전자 메일: 콘텐츠에 기반한 문서: 해시 기준)|
|기타 자그리아어|DedupedCustodians|Deduped_custodians|정확하게 중복되는 문서(해시 기준 문서를 기반으로 하는 전자 메일의 경우)|
|기타 파일 ID|DedupedFileIds|Deduped_file_IDs|정확하게 중복되는 문서의 파일 ID 목록(해시 기준 문서, 콘텐츠 기반 콘텐츠 기반)입니다.|
|문서 메모|DocComments|Doc_comments|문서 메타데이터의 설명입니다.|
|문서 회사||Doc_company|문서 메타데이터의 회사입니다.|
|DocIndex*|||제품군의 인덱스입니다. **-1** **또는 0은** 루트를 의미합니다.|
|문서 키워드||Doc_keywords|문서 메타데이터의 키워드|
|수정한 문서||Doc_modified_by|문서 메타데이터에 의해 마지막으로 수정한 날짜입니다.|
|문서 수정||Doc_revision|문서 메타데이터의 수정 내용|
|문서 제목||Doc_subject|문서 메타데이터가 적용되지 않습니다.|
|문서 서식 파일||Doc_template|문서 메타데이터의 서식 파일입니다.|
|도미니아 테마|DominantTheme|Dominant_theme|분석을 위한 계산된 도미 그룹으로|
|중복 하위 집합||Duplicate_subset|정확한 중복 항목의 그룹 ID입니다.|
|EmailAction*||Email_action|값은 **None,** **Reply 또는** **Forward**; 메시지의 제목 줄을 기반으로 합니다.|
|전자 메일 배달 확인||Email_delivery_receipt|배달 확인을 위한 인터넷 헤더에 제공된 전자 메일 주소입니다.|
|중요도|EmailImportance|Email_importance|메시지의 중요도: **0** - 낮음 **1** - 보통; **2** - 높음|
|EmailLevel*||Email_level|속하는 전자 메일 스레드 내의 메시지 수준을 나타냅니다. 첨부 파일은 상위 메시지의 값을 상속합니다.|
|전자 메일 메시지 ID||Email_message_ID|메시지의 인터넷 메시지 ID입니다.|
|EmailReadReceipt*||Email_read_receipt|읽는 확인을 위한 인터넷 헤더에 제공된 전자 메일 주소|
|전자 메일 보안|EmailSecurity|Email_security|메시지의 보안 설정: **0** - 없음; **1** - 서명됨 **2** - 암호화, **3 -** 암호화 및 서명.|
|이메일 민감도|EmailSensitivity|email_sensitivity|메시지의 민감도 설정: **0** - 없음; **1** 개인; **2** - 비공개; **3** - CompanyConfidential.|
|전자 메일 집합|EmailSet|Email_set|동일한 전자 메일 집합에 있는 모든 메시지의 그룹 ID.|
|EmailThread*||Email_thread|전자 메일 집합 내에서 메시지의 위치; 노드 ID가 루트에서 현재 메시지로 이동하며 마침표(.)로 구분됩니다.|
|추출된 콘텐츠 형식||Extracted_content_type|MIME 형식에서 추출된 콘텐츠 형식 예: **image/jpeg**|
|ExtractedTextLength*||Extracted_text_length|추출된 텍스트의 문자 수입니다.|
|가족 관련성 점수 1*||Family_relevance_score_case_issue_1|관련성에서 1가 되는 가족 관련성 점수 표현|
|FamilyDuplicateSet*||Family_duplicate_set|서로 정확히 중복되는 가정제체(동일한 콘텐츠 및 동일한 모든 첨부 파일) 패밀리의 숫자 식별자|
|패밀리 ID|FamilyId|Family_ID|가족 ID 그룹은 모든 항목을 결합하여 전자 메일의 경우 메시지와 모든 첨부 파일이 여기에 포함됩니다. 문서의 경우에는 문서와 모든 포함 항목이 포함됩니다.|
|패밀리 크기||Family_size|패밀리의 문서 수|
|파일 관련성 점수 사례 1*||File_relevance_score_case_issue_1|관련성 점수가 1인 경우. 관련성에서 1입니다.|
|File 클래스|FileClass|File_class|SharePoint 및 OneDrive 콘텐츠: **문서;** Exchange의 콘텐츠용: 전자 **메일 또는** 첨부 **파일.**|
|파일 ID|FileId|File_ID|사례 내에서 고유한 문서 식별자입니다.|
|파일 시스템 날짜||File_system_date_created|파일 시스템에서 만든 날짜(Office 365 이외의 데이터에만 적용됩니다)|
|파일 시스템 이한 날짜||File_system_date_modified|파일 시스템으로부터 수정한 날짜(Office 365 이외의 데이터에만 해당)|
|파일 형식|FileType||파일 확장명을 기반으로 하는 항목의 파일 형식입니다.|
|그룹 ID| GroupID|  |그룹화된 콘텐츠의 그룹 ID입니다.|
|첨부 파일 포함|HasAttachment|Email_has_attachment|메시지에 첨부 파일이 있는지 여부를 나타냅니다.|
|부정계|HasAttorney||**참가자** 중 하나 이상이 의견을 수있는 경우 True입니다. 그렇지 않으면 **False입니다.**|
|HasText*||Has_text|항목에 텍스트가 있는지 여부를 나타냅니다. 가능한 값은 **True및** **False입니다.**|
|변경이 허용되지 는 스스로||Immutable_ID|이 ID는 검토 집합 에서 문서를 고유하게 식별하는 데 사용됩니다. 이 필드를 검토 집합 검색에서 사용할 수 없습니다. 이 필드를 사용하여 기본 위치에서 문서에 액세스할 수 없습니다.|
|포함 형식|InclusiveType|Inclusive_type|분석을 위한 계산된 포함 형식: **0** - 포함 하지 않습니다 **1** - 전독; **2** - 포함 미로, **3** -수표가 없습니다.|
|In Reply To Id||In_reply_to_ID|메시지의 ID로 회신합니다.|
|최신 첨부 파일인 경우| IsModernAttachment|  |이 파일은 최신 첨부 파일 또는 연결된 파일입니다.|
|문서 버전을 포함하지 않습니다. | IsFromDocumentVersion |  |현재 문서가 다른 버전의 문서를 사용하여 가정되었습니다.|
|전자 메일 첨부 파일인 경우 | IsEmailAttachment|  |이 항목은 메시지에 첨부된 항목으로 표시되는 전자 메일 첨부 파일에서 보낸 항목입니다.|
|인라인 첨부 파일인 경우| IsInlineAttachment|  |이는 인라인으로 첨부되었고 메시지 본문에 표시됩니다.|
|Is Representative|IsRepresentative|Is_representative|모든 중복 항목 집합에 있는 문서가 한 개만 나타내는 문서로 표시됩니다.|
|Item 클래스|ItemClass|Item_class|Exchange Server에서 제공한 항목 클래스; 예를 들어 **IPM입니다. 참고**|
|Last modified date|LastModifiedDate|Doc_date_modified|문서 메타데이터에서 마지막으로 수정한 날짜|
|Load ID|LoadId|Load_ID|항목이 검토 집합에 추가된 로드 집합의 ID입니다.|
|위치|위치|위치|문서의 원본 위치 유형을 나타내는 문자열입니다.<br /><br />**가져온 데이터** - 비 Office 365 데이터<br />**Teams** - Microsoft Teams<br />**Exchange** - Exchange 사서함<br />**SharePoint** - SharePoint 사이트<br />**OneDrive** - OneDrive 계정|
|위치 이름|LocationName|Location_name|항목의 원본을 식별하는 문자열입니다. Exchange의 경우 이는 사서함의 SMTP 주소입니다. SharePoint 및 OneDrive의 경우 사이트 모음의 URL입니다.|
|표식으로 표시됨|MarkAsRepresentative||각각의 정확한 중복 집합에 있는 문서는 한 개만 나타내는 항목으로 표시됩니다.|
|미리 태그가 지정된 사례 문제 1*로 표시됨||Marked_as_pre_tagged_Case_issue_1|관련성에서 태그가 미리 지정된 사례 문제 1로 표시됨|
|시드 케이스 문제 1* 표시||Marked_as_seed_Case_issue_1|관련성에서 사례 1이 시드 문제 1로 표시됨|
|모임 종료 날짜|MeetingEndDate|Meeting_end_date|모임의 모임 종료 날짜입니다.|
|모임 시작 날짜|MeetingStartDate|Meeting_start_date|모임의 모임 시작 날짜입니다.|
|메시지 종류|MessageKind|Message_kind|검색할 메시지의 유형입니다. 가능한 값: ** <br /> <br /> 연락처 전자 <br /> 메일 외부 데이터 <br /> <br /> <br /> 팩스는 <br /> <br /> <br /> <br /> microsoftteams 모임을 imjournal링(Microsoft Teams에서** 의한 항목, 모임 및 통화에서 항목 반환)을 ** <br /> 메모에 <br /> <br /> 게시합니다. 바이패스 <br /> <br /> ** 작업 음성 메일| 
|기본 확장|NativeExtension|Native_extension|항목의 기본 확장입니다.|
|네이티브 파일 이름|NativeFileName|Native_file_name|항목의 네이티브 파일 이름입니다.|
|NativeMD5||Native_MD5|파일 스트림의 MD5 해시(128비트 해시 값)|
|NativeSHA256||Native_SHA_256|파일 스트림의 SHA256 해시(256비트 해시 값)|
|ND/ET 정렬: 첨부 파일 제외|NdEtSortExclAttach|ND_ET_sort_excl_attach|ET(전자 메일 스레드) 집합 및 이러한 ND(내 중복) 집합의 연결. 이 필드는 검토 시 효율적인 정렬을 수행하기 위한 용도로 사용됩니다. **D는** ND 집합 접두사로 시작되고 **E의** 접두사가 ET 집합에 접두사가 추가됩니다.|
|ND/ET 정렬: 첨부 파일 포함|NdEtSortInclAttach|ND_ET_sort_incl_attach|ET(전자 메일 스레드) 집합 및 가이드(ND) 집합의 연결. 이 필드는 검토 시 효율적인 정렬을 수행하기 위한 용도로 사용됩니다. **D는** ND 집합 접두사로 시작되고 **E의** 접두사가 ET 집합에 접두사가 추가됩니다. ET 집합의 각 전자 메일 항목 다음에 해당 첨부 파일이 그 다음에 추가됩니다.|
|정규화된 관련성 점수 1||Normalized_relevance_score_case_issue_1|관련성의 정규화된 관련성 점수 점수 를 1로 설정하세요.|
|O365 작성자||O365_authors|SharePoint에서 제작.|
|O365 생성한 사용자||O365_created_by|SharePoint에서 만든 문서|
|O365 날짜가 만들어진 날짜||O365_date_created|SharePoint에서 만든 날짜|
|수정된 O365 날짜||O365_date_modified|SharePoint에서 마지막으로 수정한 날짜|
|수정한 항목||O365_modified_by|SharePoint에서 수정합니다.|
|부모 ID|ParentId|Parent_ID|상위 항목의 ID입니다.|
|ParentNode||Parent_node|전자 메일 스레드에서 가장 가까이 에어있는 전자 메일 메시지입니다.|
|부모 경로|ParentPath|Parent_path|항목의 직접 부모의 복합 경로입니다.|
|참가자 도메인|ParticipantDomains|Email_participant_domains|메시지 참가자의 모든 도메인 목록입니다.|
|참가자|참가자|Email_participants|메시지의 모든 참가자 목록 예: Sender, To, Cc, Bcc.|
|피벗 ID|PivotId|Pivot_ID|피벗 ID입니다.|
|잠재적으로 권한 부여됨|PotentiallyPrivileged|Potentially_privileged|비상 유지 권한 검색 모델이 문서의 권한 있는 것으로 간주되는 경우 True|
|처리 상태|ProcessingStatus|Error_code|항목이 검토 집합에 추가된 후의 처리 상태입니다.|
|Read percent Case issue 1(비율 사례)||Read_percent_Case_issue_1|관련성에서 사례 1을 읽어보습니다.|
|읽기 백분위수|ReadPercentile||관련성에 따라 문서의 읽기 백분위수입니다.|
|받는 사람 수||Recipient_count|메시지를 받는 사람의 수입니다.|
|받는 사람 도메인|RecipientDomains|Email_recipient_domains|메시지의 받는 사람에 대한 모든 도메인 목록입니다.|
|받는 사람|받는 사람|Email_recipients|메시지의 받는 사람, 받는 사람, 참조, 숨은 참조)의 목록입니다.|
|관련성 부하 그룹 대수 문제 1||Relevance_load_group_case_issue_1|관련성에서 부하 그룹 사례 1을 사용합니다.|
|관련성 상태 설명||Relevance_status_description_Case_issue_1|관련성 상태 설명은 관련성의 1인치 문제입니다.|
|관련 태그 사례 1||Relevance_tag_case_issue_1|관련성에서 관련성 태그 1|
|관련성 설명||Relevance_comment|관련성의 메모 필드입니다.|
|관련성 점수|RelevanceScore||관련성을 기준으로 한 문서의 관련성 점수입니다.|
|관련 태그|RelevanceTag||관련성을 기준으로 한 문서의 관련성 점수입니다.|
|대표 ID|RepresentativeId||정확한 각 항목 집합의 숫자 식별자입니다.|
|보낸 사람|보낸 사람|Email_sender|메시지 유형의 보낸 사람(보낸 사람) 필드입니다. Format은 **DisplayName입니다. \<SmtpAddress> **|
|보낸 사람/작성자|SenderAuthor||항목을 보낸 사람이나 항목을 만든 이로 이루어 계산 필드입니다.|
|보낸 사람 도메인|SenderDomain|Email_sender_domain|보낸 사람의 도메인입니다.|
|보냅니다.|보냅니다.|Email_date_sent|메시지를 보낸 날짜입니다.|
|설정 순서: 첫 째 포함|SetOrderInclusivesFirst|Set_order_inclusives_first|필드 정렬 - 전자 메일 및 첨부 파일: 동기 알림 문서: 먼저 유사성 점수를 내어 수준을 내어서 피벗합니다.|
|SimilarityPercent||Similarity_percent|문서가 가사의 집합의 피벗과 유사한 정도를 나타냅니다.|
|네이티브 파일 크기|크기|Native_size|기본 항목의 바이트 수입니다.|
|제목|제목|Email_subject|메시지의 제목입니다.|
|제목/제목|SubjectTitle||항목의 제목이나 제목으로 계산된 계산 필드입니다.|
|사례 문제 1||Tagged_by_Case_issue_1|관련성에서 사례 문제 1을 이 문서에 태그로 지정한 사용자입니다.|
|태그|태그|태그|검토 집합에서 적용된 태그|
|테마 목록|ThemesList|Themes_list|분석에 대해 계산된 테마 목록입니다.|
|제목|제목|Doc_title|문서 메타데이터의 제목입니다.|
|받는 사람|받는 사람|Email_to|메시지 유형의 받는 사람 필드 Format은 **DisplayName입니다. \<SmtpAddress> **|
|전자 메일 집합에서 고유한 경우|UniqueInEmailSet||**전자** 메일 집합에 첨부 파일의 중복이 있는 경우 False입니다.|
|수정됨|WasRemediated|Was_Remediated|**True이면** 항목이 수정된 것이고, **False이면 False입니다.**|
|단어 개수|WordCount|Word_count|항목에 있는 단어의 개수입니다.|
|||||

> [!NOTE]
> 고급 eDiscovery 사례의 데이터를 수집할 때 Office 365 콘텐츠 위치를 검색할 때 검색 가능한 속성에 대한 자세한 내용은 콘텐츠 [검색에 대해 키워드 쿼리 및 검색 조건을 참조하세요.](keyword-queries-and-search-conditions.md)
