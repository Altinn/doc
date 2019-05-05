---
title: Endepunkter
description: Liste over alle webservice endepunkt
weight: 900
---

##### URI til alle Altinn tjenester / aliasoversikt for endepunkter

Web servicene beskrevet i dokumentet er angitt uten informasjon om endepunkt. En web service operasjon kan kalles med forskjellige endepunkter ut fra hvilken autentiseringsmetode tjenesteeier ønsker å benytte.

Det tilbys opp til tre forskjellige endepunkter for hver web service operasjon:

 - **Basic Http (SOAP 1.1).** Tradisjonell interoperabel web service hvor autentiseringsinformasjonen (brukernavn/passord) ligger i meldingen.
 - **WS Http (SOAP 1.2 med WS-Security username token).** Støtte for nye web standarder WS*, dvs. bl.a. at autentiseringsinformasjonen (brukernavn/passord) ligger i SOAP headeren.
 - **WS Http (SOAP 1.2 med WS-Security X.509 token) (markert som EC).** Støtte for ny web standarder WS*, dvs. bl.a. at
   sertifikat ligger i SOAP headeren mensbrukernavn og passord ligger i meldingen.
 - **WS Http (SOAP 1.2 med WS-Security X.509 token) (markert som AEC).** Støtte for ny web standarder WS*, dvs. bl.a. at sertifikat ligger i SOAP headeren.
   Sertifikatet må være utstedt til en organisasjon som er registrert som tjenesteeier i Altinn.

Eksempel:
Web service operasjonen "GetReceiptV2" kan aksesseres ved å kalle endepunktet "ReceiptAgencyExternal" hvis man ønsker å bruke/autentisere vha. WS* standarden. Samme operasjon finnes med navn "GetReceiptBasicV2" på endepunktet "ReceiptExternalBasic" hvis man ønsker tradisjonell web service aksessering. Tilslutt finnes det en tredje versjon av operasjonen med navn GetReceiptExternalECV2 på endepunktet "ReceiptExternalEC" hvis man ønsker å benytte virksomhetssertifikat i autentiseringen.

Her følger en aliasoversikt som viser kobling mellom operasjon og endepunkt(er) (Se også Tjenestekatalogen (Service Inventory) for informasjon om tjenesten og endepunkt):

##### ArchiveCommon

|**Basis Operasjon**|**URI/Endepunkt**|**Endepunkt operasjon**|
|--------|--------|--------|
|** ArchiveCommon**|||
|GetServiceOwnerArchiveReporteeElementsV2|WS Http https://www.altinn.no/ArchiveExternal/ArchiveCommonAgencyExternal.svc|GetServiceOwnerArchiveReporteeElementsV2|
|GetServiceOwnerArchiveReporteeElementsV2|Basic Http https://www.altinn.no/ArchiveExternal/ArchiveCommonAgencyExternalBasic.svc|GetServiceOwnerArchiveReporteeElementsBasicV2|
|GetServiceOwnerArchiveReporteeElementsV2|EC https://www.altinn.no/ArchiveExternal/ArchiveCommonAgencyExternalEC.svc|GetServiceOwnerArchiveReporteeElementsEC|
|** ServiceOwnerArchive**|||
|GetArchivedFormTaskV2|WS Http https://www.altinn.no/ArchiveExternal/ServiceOwnerArchiveExternal.svc|GetArchivedFormTaskV2|
|GetArchivedFormTaskV2|Basic Http https://www.altinn.no/ArchiveExternal/ServiceOwnerArchiveExternalBasic.svc|GetArchivedFormTaskBasicV2|
|GetArchivedFormTaskV2|EC https://www.altinn.no/ArchiveExternal/ServiceOwnerArchiveExternalEC.svc|GetArchivedFormTaskEC|
|GetArchivedFormTaskV2|EC https://www.altinn.no/ServiceEngineExternal/CaseAgencySystemEC.svc|GetCaseListAgencySystemEC|
|GetAttachmentDataStreamed|WS Http  https://www.altinn.no/ArchiveExternal/ServiceOwnerArchiveExternalStreamed.svc|GetAttachmentDataExternalStreamed|
|GetAttachmentDataStreamed|Basic Http https://www.altinn.no/ArchiveExternal/ServiceOwnerArchiveExternalStreamedBasic.svc|GetAttachmentDataStreamedBasic|
|GetAttachmentDataStreamed|EC https://www.altinn.no/ArchiveExternal/ServiceOwnerArchiveStreamedEC.svc|
|GetAttachmentDataStreamedEC|
|**Receipt**|||
| **Basis operasjon**|**URI/Endepunkt**|**Endepunkt operasjon**|
|GetReceiptV2|WS Http https://www.altinn.no/IntermediaryExternal/ReceiptAgencyExternal.svc|GetReceiptV2|
|GetReceiptV2|Basic Http https://www.altinn.no/IntermediaryExternal/ReceiptAgencyExternalBasic.svc|GetReceiptBasicV2|
|GetReceiptV2|EC https://www.altinn.no/IntermediaryExternal/ReceiptAgencyExternalEC.svc|GetReceiptECV2|
|GetReceiptListV2|WS Http https://www.altinn.no/IntermediaryExternal/ReceiptAgencyExternal.svc|GetReceiptListV2|
|GetReceiptListV2|Basic Http https://www.altinn.no/IntermediaryExternal/ReceiptAgencyExternalBasic.svc|GetReceiptListBasicV2|
|GetReceiptListV2|EC https://www.altinn.no/IntermediaryExternal/ReceiptAgencyExternalEC.svc|GetReceiptListECV2|
|UpdateReceipt|WS Http https://www.altinn.no/IntermediaryExternal/ReceiptAgencyExternal.svc|UpdateReceipt|
|UpdateReceipt|Basic Http https://www.altinn.no/IntermediaryExternal/ReceiptAgencyExternalBasic.svc|UpdateReceiptBasic|
|UpdateReceipt|EC https://www.altinn.no/IntermediaryExternal/ReceiptAgencyExternalEC.svc|UpdateReceiptEC|
|**CaseAgencySystem**|||
|**Basis operasjon**|**URI/Endepunkt**|**Endepunkt operasjon**|
|InstantiateCollaborationAgencySystem|WS Http https://www.altinn.no/ServiceEngineExternal/CaseAgencySystemExternal.svc|InstantiateCollaborationAgencySystemExternal|
|InstantiateCollaborationAgencySystem|Basic Http https://www.altinn.no/ServiceEngineExternal/CaseAgencySystemExternalBasic.svc|InstantiateCollaborationAgencySystemExternalBasic|InstantiateCollaborationAgencySystemExternalBasic|
|InstantiateCollaborationAgencySystem|EC https://www.altinn.no/ServiceEngineExternal/CaseAgencySystemEC.svc|InstantiateCollaborationAgencySystemEC|
|GetCaseListAgencySystem|WS Http https://www.altinn.no/ServiceEngineExternal/CaseAgencySystemExternal.svc|GetCaseListAgencySystemExternal|
|GetCaseListAgencySystem|Basic Http https://www.altinn.no/ServiceEngineExternal/CaseAgencySystemExternalBasic.svc|GetCaseListAgencySystemExternalBasic|
|GetCaseListAgencySystem|EC https://www.altinn.no/ServiceEngineExternal/CaseAgencySystemEC.svc|GetCaseListAgencySystemEC|
|NotifyEventAgencySystem|WS Http https://www.altinn.no/ServiceEngineExternal/CaseAgencySystemExternal.svc|NotifyEventAgencySystemExternal|
|NotifyEventAgencySystem|Basic Http https://www.altinn.no/ServiceEngineExternal/CaseAgencySystemExternalBasic.svc|NotifyEventAgencySystemExternalBasic|
|NotifyEventAgencySystem|EC https://www.altinn.no/ServiceEngineExternal/CaseAgencySystemEC.svc|NotifyEventAgencySystemEC|
|SetNoticeAgencySystem|WS Http https://www.altinn.no/ServiceEngineExternal/CaseAgencySystemExternal.svc|SetNoticeAgencySystemExternal|
|SetNoticeAgencySystem|Basic Http https://www.altinn.no/ServiceEngineExternal/CaseAgencySystemExternalBasic.svc|SetNoticeAgencySystemExternalBasic|
|SetNoticeAgencySystem|EC https://www.altinn.no/ServiceEngineExternal/CaseAgencySystemEC.svc|SetNoticeAgencySystemEC|
|**Correspondence**|||
|**Basis operasjon**|**URI/Endepunkt**|**Endepunkt operasjon**|
|InsertCorrespondenceV2|WS Http https://www.altinn.no/ServiceEngineExternal/CorrespondenceAgencyExternal.svc|InsertCorrespondenceV2|
|InsertCorrespondenceV2|Basic Http https://www.altinn.no/ServiceEngineExternal/CorrespondenceAgencyExternalBasic.svc|InsertCorrespondenceBasicV2|
|InsertCorrespondenceV2|EC https://www.altinn.no/ServiceEngineExternal/CorrespondenceAgencyExternalEC.svc|InsertCorrespondenceEC|
|InsertCorrespondenceV2|AEC https://www.altinn.no/ServiceEngineExternal/CorrespondenceAgencyExternalAEC.svc|InsertCorrespondenceAEC|
|CreateSimpleCorrespondenceService|WS Http https://www.altinn.no/ServiceEngineExternal/CorrespondenceAgencyExternal.svc|CreateSimpleCorrespondenceService|
|CreateSimpleCorrespondenceService|Basic Http https://www.altinn.no/ServiceEngineExternal/CorrespondenceAgencyExternalBasic.svc|CreateSimpleCorrespondenceServiceBasic|
|CreateSimpleCorrespondenceService|EC Ikke tilgjengelig på dette grensesnittet||
|CreateSimpleCorrespondenceService|AEC Ikke tilgjengelig på dette grensesnittet||
|GetCorrespondenceStatusDetailsV3|WS Http https://www.altinn.no/ServiceEngineExternal/CorrespondenceAgencyExternal.svc|GetCorrespondenceStatusDetailsV3|
|GetCorrespondenceStatusDetailsV3|Basic Http https://www.altinn.no/ServiceEngineExternal/CorrespondenceAgencyExternalBasic.svc|GetCorrespondenceStatusDetailsBasicV3|
|GetCorrespondenceStatusDetailsV3|EC https://www.altinn.no/ServiceEngineExternal/CorrespondenceAgencyExternalEC.svc|GetCorrespondenceStatusDetailsECV3|
|GetCorrespondenceStatusDetailsV3|AEC https://www.altinn.no/ServiceEngineExternal/CorrespondenceAgencyExternalAEC.svc|GetCorrespondenceStatusDetailsAECV3|
|GetCorrespondenceStatusHistory|WS Http https://www.altinn.no/ServiceEngineExternal/CorrespondenceAgencyExternal.svc|GetCorrespondenceStatusHistory|
|GetCorrespondenceStatusHistory|Basic Http https://www.altinn.no/ServiceEngineExternal/CorrespondenceAgencyExternalBasic.svc|GetCorrespondenceStatusHistoryBasic|
|GetCorrespondenceStatusHistory|EC https://www.altinn.no/ServiceEngineExternal/CorrespondenceAgencyExternalEC.svc|GetCorrespondenceStatusHistoryEC|
|GetCorrespondenceStatusHistory|AEC https://www.altinn.no/ServiceEngineExternal/CorrespondenceAgencyExternalAEC.svc|GetCorrespondenceStatusHistoryAEC|
|**AltUt**|||
|**Basis operasjon**|**URI/Endepunkt**|**Endepunkt operasjon**|
|SubmitAltutMessagePw|Basic Http https://www.altinn.no/webservicesAgency/AgencydataExchange.asmx?op=SubmitAltutMessagePw|SubmitAltutMessagePw|
|**Prefill**|||
|**Basis operasjon**|**URI/Endepunkt**|**Endepunkt operasjon**|
|SubmitAndInstantiatePrefilledFormTask|WS Http https://www.altinn.no/ServiceEngineExternal/Prefill.svc|SubmitAndInstantiatePrefilledFormTask|
|SubmitAndInstantiatePrefilledFormTask|Basic Http https://www.altinn.no/ServiceEngineExternal/PrefillBasic.svc|SubmitAndInstantiatePrefilledFormTaskBasic|
|SubmitAndInstantiatePrefilledFormTask|EC https://www.altinn.no/ServiceEngineExternal/PreFillAgencyExternalEC.svc|SubmitAndInstantiatePrefilledFormTaskEC|
|SubmitPrefilledFormTasks|WS Http https://www.altinn.no/ServiceEngineExternal/Prefill.svc|SubmitPrefilledFormTasks|
|SubmitPrefilledFormTasks|Basic Http https://www.altinn.no/ServiceEngineExternal/PrefillBasic.svc|SubmitPrefilledFormTasksBasic|
|SubmitPrefilledFormTasks|EC https://www.altinn.no/ServiceEngineExternal/PreFillAgencyExternalEC.svc|SubmitPrefilledFormTasksEC|
|**Subscription**|||
|**Basis operasjon**|**URI/Endepunkt**|**Endepunkt operasjon**|
|SubmitSubscription|WS Http https://www.altinn.no/ServiceEngineExternal/Subscription.svc|SubmitSubscription|
|SubmitSubscription|Basic Http https://www.altinn.no/ServiceEngineExternal/SubscriptionBasic.svc|SubmitSubscriptionBasic|
|SubmitSubscription|EC https://www.altinn.no/ServiceEngineExternal/SubscriptionAgencyExternalEC.svc|SubmitSubscriptionEC|
|**NotificationAgencyExternal**|||
|**Basis operasjon**|**URI/Endepunkt**|**Endepunkt operasjon**|
|SendStandaloneNotification|WS Http https://www.altinn.no/ServiceEngineExternal/NotificationAgencyExternal.svc|SendStandaloneNotification|
|SendStandaloneNotification|Basic Http https://www.altinn.no/ServiceEngineExternal/NotificationAgencyExternalBasic.svc|SendStandaloneNotificationBasic|
|SendStandaloneNotification|EC https://www.altinn.no/ServiceEngineExternal/NotificationAgencyExternalEC.svc|SendStandaloneNotificationEC|
|**AuthorizationAdministration**|||
|**Basis operasjon**|**URI/Endepunkt**|**Endepunkt operasjon**|
|ImportAuthorizationPolicy|WS Http https://www.altinn.no/AuthorizationExternal/AdministrationExternal.svc|ImportAuthorizationPolicy|
|GetReporteeByTempKey|WS Http https://www.altinn.no/AuthorizationExternal/AdministrationExternal.svc|GetReporteeByTempKey|
|GetReportees|WS Http https://www.altinn.no/AuthorizationExternal/AdministrationExternal.svc|GetReportees|
|GetRoles|WS Http https://www.altinn.no/AuthorizationExternal/AdministrationExternal.svc|GetRoles|
|**AuthorizationDecisionPointExternal**|||
|**Basis operasjon**|**URI/Endepunkt**|**Endepunkt operasjon**|
|AuthorizeAccessExternal|WS Http https://www.altinn.no/AuthorizationExternal/AuthorizationDecisionPointExternal.svc|AuthorizeAccessExternal|
|**DownloadQueueExternal**|||
|**Basis operasjon**|**URI/Endepunkt**|**Endepunkt operasjon**|
|GetDownloadQueueItems|WS Http https://www.altinn.no/ArchiveExternal/DownloadQueueExternal.svc|GetDownloadQueueItems|
|GetDownloadQueueItems|WS Http https://www.altinn.no/ArchiveExternal/DownloadQueueExternalBasic.svc|GetDownloadQueueItems|
|GetDownloadQueueItems|WS Http https://www.altinn.no/ArchiveExternal/DownloadQueueExternalEC.svc|GetDownloadQueueItems|
|PurgeItem|WS Http https://www.altinn.no/ArchiveExternal/DownloadQueueExternal.svc|PurgeItem|
|PurgeItem|WS Http https://www.altinn.no/ArchiveExternal/DownloadQueueExternalBasic.svc|PurgeItem|
|PurgeItem|WS Http https://www.altinn.no/ArchiveExternal/DownloadQueueExternalEC.svc|PurgeItem|
|GetArchivedFormTask|WS Http https://www.altinn.no/ArchiveExternal/DownloadQueueExternal.svc|GetArchivedFormTaskExternalDQ|
|GetArchivedFormTask|WS Http https://www.altinn.no/ArchiveExternal/DownloadQueueExternalBasic.svc|GetArchivedFormTaskBasicDQ|
|GetArchivedFormTask|WS Http https://www.altinn.no/ArchiveExternal/DownloadQueueExternalEC.svc|GetArchivedFormTaskECDQ|
|**ContextHandlerExternal**|||
|**Basis operasjon**|**URI/Endepunkt**|**Endepunkt operasjon**|
|GetReporteeElementContextExternal|WS Http https://www.altinn.no/ServiceEngineExternal/ContextHandlerExternal.svc|GetReporteeElementContextExternal|
|GetReporteeElementContextExternal|Basic Http https://www.altinn.no/ServiceEngineExternal/ContextHandlerExternalBasic.svc|GetReporteeElementContextExternalBasic|
|GetReporteeElementContextExternal|EC https://www.altinn.no/ServiceEngineExternal/ContextHandlerEC.svc|GetReporteeElementContextExternalEC|
|**RegisterSSRAgencyExternal**|
|**Basis operasjon**|**URI/Endepunkt**|**Endepunkt operasjon**|
|GetRights|WS Http https://www.altinn.no/RegisterExternal/RegisterSRRAgencyExternal.svc|GetRights|
|GetRights|Basic Http https://www.altinn.no/RegisterExternal/RegisterSRRAgencyExternalBasic.svc|GetRightsBasic|
|GetRights|EC https://www.altinn.no/RegisterExternal/RegisterSRRAgencyExternalEC.svc|GetRightsEC|
|AddRights|WS Http https://www.altinn.no/RegisterExternal/RegisterSRRAgencyExternal.svc|AddRights|
|AddRights|Basic Http https://www.altinn.no/RegisterExternal/RegisterSRRAgencyExternalBasic.svc|AddRightsBasic|
|AddRights|EC https://www.altinn.no/RegisterExternal/RegisterSRRAgencyExternalEC.svc|AddRightsEC|
|DeleteRights|WS Http https://www.altinn.no/RegisterExternal/RegisterSRRAgencyExternal.svc|DeleteRights|
|DeleteRights|Basic Http https://www.altinn.no/RegisterExternal/RegisterSRRAgencyExternalBasic.svc|DeleteRightsBasic|
|DeleteRights|EC https://www.altinn.no/RegisterExternal/RegisterSRRAgencyExternalEC.svc|DeleteRightsEC|
Alle URI er angitt med produksjonsadresse. Frem til produksjonssetting må https://www.altinn.no erstattes med peker til testmiljø.
