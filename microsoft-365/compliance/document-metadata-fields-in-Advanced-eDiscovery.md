---
title: Advanced eDiscovery의 문서 메타데이터 필드
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 이 문서에서는 Microsoft 365의 Advanced eDiscovery 사례에서 검토 집합의 문서에 대한 메타데이터 필드를 정의합니다.
ms.openlocfilehash: 3f8ac33e3f11557843b590ed2a9f7d903e33f5ea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922062"
---
# <a name="document-metadata-fields-in-advanced-ediscovery"></a>Advanced eDiscovery의 문서 메타데이터 필드

다음 표에는 Advanced eDiscovery의 사례 집합에 있는 검토 집합의 문서에 대한 메타데이터 필드가 나열되어 있습니다. 이 표에서는 다음 정보를 제공합니다.

- **필드 이름** 및 표시 필드 **이름:** 검토 집합에서 선택한 문서의 파일 메타데이터를 볼 때 표시되는 필드 이름과 메타데이터 필드의 이름입니다. 일부 메타데이터 필드는 문서의 파일 메타데이터를 볼 때 포함되지 않습니다. 이러한 필드는 추가 표시(*)로 강조 표시됩니다.

- **검색 가능한 필드 이름:** 검토 집합 쿼리를 실행하는 경우 검색할 수 있는 [속성의 이름입니다.](review-set-search.md) 빈 셀은 검토 집합 쿼리에서 필드를 검색할 수 없습니다.

- **내보낼 필드 이름:** 문서를 내보낼 때 포함된 메타데이터 필드의 이름입니다.  빈 셀은 필드가 내보낼 메타데이터에 포함되지 않음을 의미합니다.

- **설명:** 메타데이터 필드에 대한 설명입니다.

> [!NOTE]
> 검토 **집합 검색의** 키워드 [필드는](./review-set-search.md) KQL(키워드 쿼리 언어)을 사용합니다. 검색 가능한 필드  이름 열에 나열된 필드는 검토 집합 검색의 키워드 필드에서 쿼리 작성기 없이 복잡한 쿼리를 작성하는 데 사용할 수 있습니다.  KQL에 대한 자세한 내용은 키워드 쿼리 [언어 구문 참조 를 참조하세요.](/sharepoint/dev/general-development/keyword-query-language-kql-syntax-reference)

|**필드 이름** 및 **표시 필드 이름**|**검색 가능한 필드 이름**|**내보낼 필드 이름**|**설명**|
|:-----|:-----|:-----|:-----|
|첨부 파일 콘텐츠 ID|AttachmentContentId||항목의 첨부 파일 콘텐츠 ID입니다.|
|첨부 파일 이름|AttachmentNames|Attachment_Names|첨부 파일 이름 목록입니다.|
|변호사 클라이언트 권한 점수|AttorneyClientPrivilegeScore||변호사-클라이언트 권한 모델 콘텐츠 점수입니다.|
|만든 이|만든 이|Doc_authors|문서 메타데이터를 사용하여 작성합니다.|
|BCC|Bcc|Email_bcc|메시지 유형에 대한 Bcc 필드입니다. 형식은 **DisplayName \<SMTPAddress> 입니다.**|
|CC|Cc|Email_cc|메시지 유형에 대한Cc 필드입니다. 형식은 **DisplayName \<SMTPAddress> 입니다.**|
|규정 준수 레이블|ComplianceLabels|Compliance_labels|[](retention.md) Office 365의 콘텐츠에 적용된 보존 레이블입니다.|
|복합 경로|CompoundPath|Compound_path|항목의 원본을 설명하는 사람이 읽을 수 있는 경로입니다.|
|콘텐츠*|콘텐츠||항목의 추출된 텍스트입니다.|
|Conversation Body|Conversation Body||항목의 대화 본문입니다.|
|대화 항목|대화 항목||항목의 대화 항목입니다.|
|대화 ID|ConversationId|Conversation_ID|메시지의 대화 ID입니다.|
|대화 인덱스||Conversation_index|메시지의 대화 인덱스입니다.|
|대화 Pdf 시간|ConversationPdfTime||PDF 버전의 대화가 만들어진 날짜입니다.|
|대화 재배포 굽기 시간|ConversationRedactionBurnTime||채팅을 위해 대화의 PDF 버전을 만든 날짜입니다.|
|만든 문서 날짜|CreatedTime|Doc_date_created|문서 메타데이터에서 날짜를 생성합니다.|
|Custodian|Custodian|Custodian|항목이 연결된 수장의 이름입니다.|
|날짜|날짜|날짜|Date는 파일 형식에 따라 계산된 필드입니다.<br /><br />전자 메일: 보낸 날짜<br />전자 메일 첨부 파일: 문서의 마지막 수정 날짜입니다. 사용할 수 없는 경우 부모의 보낸 날짜<br />포함된 문서: 문서의 마지막 수정 날짜 사용할 수 없는 경우 부모의 마지막 수정 날짜<br />SPO 문서(최신 첨부 파일 포함): SharePoint 마지막으로 수정한 날짜 사용할 수 없는 경우 문서가 마지막으로 수정된 날짜입니다.<br />비 Office 365 문서: 마지막으로 수정한 날짜<br />모임: 모임 시작 날짜<br />VoiceMail: 보낸 날짜<br />IM: 보낸 날짜|
|기타 경로|Dedupedcompoundpath|Deduped_compound_path|정확히 중복되는 문서의 복합 경로 목록입니다(전자 메일: 콘텐츠 기반, 문서: 해시 기반).|
|기타 보전자|DedupedCustodians|Deduped_custodians|정확히 중복되는 문서의 보위자 목록입니다(콘텐츠에 따라 전자 메일의 경우, 문서의 경우 해시 기반).|
|기타 파일 ID|DedupedFileIds|Deduped_file_IDs|정확히 중복되는 문서의 파일 신분증 목록입니다(전자 메일의 경우 콘텐츠 기반, 문서의 경우 해시 기반).|
|문서 설명|DocComments|Doc_comments|문서 메타데이터의 설명입니다.|
|문서 회사||Doc_company|문서 메타데이터의 회사입니다.|
|DocIndex*|||패밀리의 인덱스입니다. **-1** 또는 **0은** 루트를 의미합니다.|
|문서 키워드||Doc_keywords|문서 메타데이터의 키워드입니다.|
|수정한 문서||Doc_modified_by|문서 메타데이터에서 마지막으로 수정한 날짜입니다.|
|문서 변경||Doc_revision|문서 메타데이터에서 변경합니다.|
|문서 제목||Doc_subject|문서 메타데이터의 제목입니다.|
|문서 서식 파일||Doc_template|문서 메타데이터의 서식 파일입니다.|
|주 테마|DominantTheme|Dominant_theme|분석에 대해 계산된 주 테마입니다.|
|중복 하위 집합||Duplicate_subset|정확한 중복 항목의 그룹 ID입니다.|
|EmailAction*||Email_action|값은 **None,** **Reply** 또는 **Forward입니다.** 메시지의 제목 줄을 기반으로 합니다.|
|전자 메일 배달 확인||Email_delivery_receipt|배달 확인을 위해 인터넷 헤더에 제공된 전자 메일 주소입니다.|
|Importance|EmailImportance|Email_importance|메시지의 중요도: **0** - 낮음 **1** - 보통; **2** - 높음|
|EmailLevel*||Email_level|메시지가 속한 전자 메일 스레드 내의 메시지 수준을 나타냅니다. 첨부 파일은 부모 메시지의 값을 상속합니다.|
|전자 메일 메시지 ID||Email_message_ID|메시지의 인터넷 메시지 ID입니다.|
|EmailReadReceipt*||Email_read_receipt|읽은 확인을 위해 인터넷 헤더에 제공된 전자 메일 주소입니다.|
|전자 메일 보안|EmailSecurity|Email_security|메시지의 보안 설정: **0** - 없음; **1** - 서명된; **2** - 암호화 **3** - 암호화되고 서명된 경우.|
|전자 메일 민감도|EmailSensitivity|email_sensitivity|메시지의 민감도 설정: **0** - 없음; **1** 개인; **2** - 비공개; **3** - CompanyConfidential.|
|전자 메일 집합|EmailSet|Email_set|동일한 전자 메일 집합의 모든 메시지에 대한 그룹 ID입니다.|
|EmailThread*||Email_thread|전자 메일 집합 내에서 메시지의 위치입니다. 루트에서 현재 메시지까지의 노드 ID로 구성하며 기간(.)으로 구분됩니다.|
|추출된 콘텐츠 형식||Extracted_content_type|Mime 형식의 추출된 콘텐츠 형식 예: **image/jpeg**|
|ExtractedTextLength*||Extracted_text_length|추출된 텍스트의 문자 수입니다.|
|가족과 무관성 점수 사례 문제 1*||Family_relevance_score_case_issue_1|가족과의 무관성 점수의 사례 1입니다.|
|FamilyDuplicateSet*||Family_duplicate_set|서로 정확히 중복되는 패밀리의 숫자 식별자입니다(동일한 콘텐츠 및 모든 동일한 첨부 파일).|
|가족 ID|FamilyId|Family_ID|패밀리 ID는 모든 항목을 함께 그룹화합니다. 전자 메일의 경우 메시지와 모든 첨부 파일이 포함됩니다. 문서의 경우 문서 및 포함된 항목이 포함됩니다.|
|가족 크기||Family_size|패밀리의 문서 수입니다.|
|파일 타당성 점수 사례 문제 1*||File_relevance_score_case_issue_1|파일 타당성 점수의 사례 문제 1()입니다.|
|파일 클래스|FileClass|File_class|SharePoint 및 OneDrive의 콘텐츠: **문서**; Exchange의 콘텐츠: **전자 메일** 또는 첨부 파일 . |
|파일 ID|FileId|File_ID|사례 내에서 고유한 문서 식별자입니다.|
|만들어진 파일 시스템 날짜||File_system_date_created|파일 시스템에서 만든 날짜입니다(Office 365가 아닌 데이터에만 적용).|
|파일 시스템 날짜 수정||File_system_date_modified|파일 시스템에서 수정된 날짜입니다(Office 365가 아닌 데이터에만 적용).|
|파일 형식|FileType||파일 확장명에 따라 항목의 파일 형식입니다.|
|그룹 ID| GroupID|  |그룹화한 콘텐츠의 그룹 ID입니다.|
|첨부 파일 포함|HasAttachment|Email_has_attachment|메시지에 첨부 파일이 있는지 여부를 나타냅니다.|
|변호사가 있습니다.|HasAttorney||**True이면** 적어도 한 명 이상의 참가자가 변호사 목록에 있습니다. 그렇지 않으면 값이 **False입니다.**|
|HasText*||Has_text|항목에 텍스트가 있는지 여부를 나타냅니다. 가능한 값은 **True** 및 **False입니다.**|
|Immutable ID||Immutable_ID|이 ID는 검토 집합 내에서 문서를 고유하게 식별하는 데 사용됩니다. 이 필드는 검토 집합 검색에 사용할 수 없습니다. ID를 사용하여 해당 기본 위치에 있는 문서에 액세스할 수 없습니다.|
|포괄 유형|InclusiveType|Inclusive_type|분석에 대해 계산된 포함 유형: **0** - 포괄이 아지 않습니다. **1** - 포괄; **2** - 포괄 마이너스 **3** - 포괄 복사본입니다.|
|Id에 회신||In_reply_to_ID|메시지에서 ID에 회신합니다.|
|최신 첨부 파일| IsModernAttachment|  |이 파일은 최신 첨부 파일 또는 연결된 파일입니다.|
|문서 버전에서 | IsFromDocumentVersion |  |현재 문서가 다른 버전의 다른 문서에 있습니다.|
|전자 메일 첨부 파일 | IsEmailAttachment|  |이 항목은 메시지에 첨부된 항목으로 표시하는 전자 메일 첨부 파일에서 전송됩니다.|
|인라인 첨부 파일| IsInlineAttachment|  |이 인라인이 첨부되어 메시지 본문에 표시됩니다.|
|Is Representative|IsRepresentative|Is_representative|정확한 중복 항목 집합에 있는 문서 한 개가 대표 문서로 표시됩니다.|
|Item 클래스|ItemClass|Item_class|Exchange 서버에서 제공하는 항목 클래스 예를 들어 **IPM을 예로 들 수 있습니다. 참고**|
|Last modified date|LastModifiedDate|Doc_date_modified|문서 메타데이터에서 마지막으로 수정한 날짜입니다.|
|로드 ID|LoadId|Load_ID|항목이 검토 집합에 추가된 로드 집합의 ID입니다.|
|위치|위치|위치|문서가 원본으로 사용된 위치의 유형을 나타내는 문자열입니다.<br /><br />**가져온 데이터** - Office 365 이 아닌 데이터<br />**Teams** - Microsoft Teams<br />**Exchange** - Exchange 사서함<br />**SharePoint** - SharePoint 사이트<br />**OneDrive** - OneDrive 계정|
|위치 이름|LocationName|Location_name|항목의 원본을 식별하는 문자열입니다. Exchange의 경우 사서함의 SMTP 주소입니다. SharePoint 및 OneDrive의 경우 사이트 모음의 URL입니다.|
|대표로 표시|MarkAsRepresentative||각 중복 집합의 문서 한 개가 담당자로 표시됩니다.|
|미리 태그가 지정 된 사례 문제 1*||Marked_as_pre_tagged_Case_issue_1|사전 태그가 지정한 사례 문제 1(Relevance)로 표시|
|시드 사례 문제 1*로 표시||Marked_as_seed_Case_issue_1|참조에서 시드 사례 문제 1로 표시됩니다.|
|모임 종료 날짜|MeetingEndDate|Meeting_end_date|모임의 모임 종료 날짜입니다.|
|모임 시작 날짜|MeetingStartDate|Meeting_start_date|모임의 모임 시작 날짜입니다.|
|메시지 종류|MessageKind|Message_kind|검색할 메시지 유형입니다. 가능한 **<br /> <br /> 값: 연락처 <br /> docs 전자 <br /> 메일 <br /> externaldata <br /> 팩스 im <br /> <br /> 저널스 <br /> 모임 <br /> microsoftteams(Microsoft** Teams에서 채팅, 모임 및 통화의 항목 반환) 메모 게시물 **<br /> <br /> <br /> rssfeeds <br /> 작업 음성 <br /> 메일**| 
|Native Extension|NativeExtension|Native_extension|항목의 기본 확장명입니다.|
|기본 파일 이름|NativeFileName|Native_file_name|항목의 기본 파일 이름입니다.|
|NativeMD5||Native_MD5|파일 스트림의 MD5 해시(128비트 해시 값)|
|NativeSHA256||Native_SHA_256|파일 스트림의 SHA256 해시(256비트 해시 값)|
|ND/ET 정렬: 첨부 파일 제외|NdEtSortExclAttach|ND_ET_sort_excl_attach|ET(전자 메일 스레드) 집합 및 ND(Near-duplicate) 집합의 연속입니다. 이 필드는 검토 시 효율적으로 정렬하는 데 사용됩니다. **D는** ND 집합에, **E는** ET 집합에 사전으로 추가됩니다.|
|ND/ET 정렬: 첨부 파일 포함|NdEtSortInclAttach|ND_ET_sort_incl_attach|ET(전자 메일 스레드) 집합과 중복에 가까운 ND(복제본) 집합의 연속입니다. 이 필드는 검토 시 효율적으로 정렬하는 데 사용됩니다. **D는** ND 집합에, **E는** ET 집합에 사전으로 추가됩니다. ET 집합의 각 전자 메일 항목 다음에는 해당 첨부 파일이 표시됩니다.|
|정규화된관일성 점수 사례 1||Normalized_relevance_score_case_issue_1|정규화된관일성 점수의 대소문자 문제 1|
|O365 작성자||O365_authors|SharePoint에서 작성자.|
|O365에서 만든 O365||O365_created_by|SharePoint에서 만든 것입니다.|
|O365 만든 날짜||O365_date_created|SharePoint에서 만든 날짜입니다.|
|O365 날짜 수정||O365_date_modified|SharePoint에서 마지막으로 수정한 날짜입니다.|
|O365에 의해 수정||O365_modified_by|SharePoint에서 수정되었습니다.|
|상위 ID|ParentId|Parent_ID|항목의 부모 ID입니다.|
|ParentNode||Parent_node|전자 메일 스레드에서 가장 앞의 전자 메일 메시지입니다.|
|상위 경로|ParentPath|Parent_path|항목의 직접 상위 항목의 복합 경로입니다.|
|참가자 도메인|ParticipantDomains|Email_participant_domains|메시지 참가자의 모든 도메인 목록입니다.|
|참가자|참가자|Email_participants|메시지의 모든 참가자 목록 예를 들어 Sender, To, Cc, Bcc와 같습니다.|
|피벗 ID|PivotId|Pivot_ID|피벗의 ID입니다.|
|권한이 부여될 수 있습니다.|PotentiallyPrivileged|Potentially_privileged|True이면 변호사-클라이언트 권한 검색 모델에서 문서를 잠재적으로 권한이 부여된 것으로 고려합니다.|
|처리 상태|ProcessingStatus|Error_code|항목이 검토 집합에 추가된 후의 처리 상태입니다.|
|읽기 비율 사례 문제 1||Read_percent_Case_issue_1|읽은 백분율의 사례 문제 1(1)을(를) 읽어 읽습니다.|
|읽기 백분위수|ReadPercentile||관련성에 따라 문서의 백분위수 읽기|
|받는 사람 수||Recipient_count|메시지의 받는 사람 수입니다.|
|받는 사람 도메인|RecipientDomains|Email_recipient_domains|메시지 받는 사람의 모든 도메인 목록입니다.|
|받는 사람|받는 사람|Email_recipients|메시지의 모든 받는 사람(받는 사람,Cc, Bcc)의 목록입니다.|
|문제 1과의관성 로드 그룹 사례 1||Relevance_load_group_case_issue_1|Relevance load group Case issue 1 from Relevance.|
|해당 상태 설명 사례 문제 1||Relevance_status_description_Case_issue_1|Relevance status description Case issue 1 from Relevance.|
|타당성 태그 사례 문제 1||Relevance_tag_case_issue_1|Relevance tag Case issue 1 from Relevance.|
|Relevance Comment||Relevance_comment|Relevance의 설명 필드입니다.|
|타당성 점수|RelevanceScore||관련성에 따라 문서의 관련성 점수입니다.|
|Relevance tag|RelevanceTag||관련성에 따라 문서의 관련성 점수입니다.|
|대표 ID|RepresentativeId||정확한 중복 집합의 각 집합에 대한 숫자 식별자입니다.|
|보낸 사람|보낸 사람|Email_sender|메시지 유형에 대한 보낸 사람(보낸 사람) 필드입니다. 형식은 **DisplayName \<SmtpAddress> 입니다.**|
|보낸 사람/만든 이|SenderAuthor||항목을 보낸 사람 또는 만든 이로 구성된 계산 필드입니다.|
|보낸 사람 도메인|SenderDomain|Email_sender_domain|보낸 사람 도메인입니다.|
|Sent|Sent|Email_date_sent|메시지의 보낸 날짜입니다.|
|순서 설정: 우선 포함|SetOrderInclusivesFirst|Set_order_inclusives_first|정렬 필드 - 전자 메일 및 첨부 파일: 연도에 반시적; 문서: 먼저 유사성 점수를 내어 피벗합니다.|
|SimilarityPercent||Similarity_percent|문서가 가까운 중복 집합의 피벗과 얼마나 유사한지 나타냅니다.|
|기본 파일 크기|Size|Native_size|기본 항목의 bytes 수입니다.|
|제목|제목|Email_subject|메시지의 제목입니다.|
|제목/제목|SubjectTitle||항목의 제목 또는 제목으로 구성된 계산 필드입니다.|
|사례 문제 1로 태그 지정||Tagged_by_Case_issue_1|관련성에서 사례 문제 1에 이 문서에 태그를 지정한 사용자입니다.|
|태그|태그|태그|검토 집합에 적용된 태그입니다.|
|테마 목록|ThemesList|Themes_list|분석에 대해 계산된 테마 목록입니다.|
|제목|제목|Doc_title|문서 메타데이터의 제목입니다.|
|받는 사람|받는 사람|Email_to|To 메시지 유형에 대한 필드입니다. Format은 **DisplayName입니다. \<SmtpAddress>**|
|전자 메일 집합의 고유|UniqueInEmailSet||**False이면** 첨부 파일이 전자 메일 집합에 중복되어 있습니다.|
|수정된 경우|WasRemediated|Was_Remediated|**True이면** 항목이 수정된 것입니다. 그렇지 않으면 **False입니다.**|
|단어 개수|WordCount|Word_count|항목의 단어 수입니다.|
|||||

> [!NOTE]
> Advanced eDiscovery 사례에 대한 데이터를 수집할 때 Office 365 콘텐츠 위치를 검색할 때 검색 가능한 속성에 대한 자세한 내용은 콘텐츠 검색에 대한 키워드 쿼리 및 검색 조건을 [참조하세요.](keyword-queries-and-search-conditions.md)