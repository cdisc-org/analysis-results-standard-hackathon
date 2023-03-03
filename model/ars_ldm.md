```mermaid
erDiagram
ReportingEvent {
    string name  
}
Output {
    string id  
    integer version  
}
AnalysisCategory {
    string id  
    string label  
}
AnalysisCategorization {
    string id  
    string label  
}
OutputDisplay {
    integer order  
}
Display {
    string id  
    integer version  
    string displayTitle  
    string name  
}
DisplaySection {
    SectionType sectionType  
}
DisplaySubSection {
    string id  
    integer order  
    string text  
}
File {
    FileType fileType  
    string location  
    string style  
    string name  
}
Analysis {
    string id  
    integer version  
    string dataset  
    string variable  
}
AnalysisMethod {
    string id  
    string label  
    string description  
    string name  
}
Operation {
    string id  
    string label  
    string resultPattern  
    string name  
}
OperationResult {
    string rawValue  
    string formattedValue  
}
AnalysisGroup {
    string label  
    integer order  
    string id  
}
CompoundGroupExpression {
    AndOr logicalOperator  
}
Group {
    string label  
    integer order  
    string id  
}
Condition {
    string dataset  
    string variable  
    Comparator comparator  
    stringList value  
}
ReferencedResultRelationship {
    OperationRole referencedResultRole  
}
DataSubset {
    string label  
    string id  
}
CompoundSubsetExpression {
    AndOr logicalOperator  
}
WhereClause {
    string id  
}
CompoundExpression {
    AndOr logicalOperator  
}
OrderedGroupingFactor {
    integer order  
}
DataGroupingFactor {
    string id  
    string label  
    string groupingVariable  
    boolean dataDriven  
}
DataGroup {
    string label  
    integer order  
    string id  
}
GroupingFactor {
    string id  
    string label  
    string groupingVariable  
    boolean dataDriven  
}
AnalysisSet {
    string label  
    integer order  
    string id  
}
CompoundSetExpression {
    AndOr logicalOperator  
}
SubjectGroupingFactor {
    string id  
    string label  
    string groupingVariable  
    boolean dataDriven  
}
NestedList {

}
OrderedListItem {
    integer order  
    string name  
}

ReportingEvent ||--|| NestedList : "listOfPlannedAnalyses"
ReportingEvent ||--|o NestedList : "listOfPlannedOutputs"
ReportingEvent ||--}o AnalysisSet : "analysisSets"
ReportingEvent ||--}o SubjectGroupingFactor : "analysisGroupings"
ReportingEvent ||--}o DataSubset : "dataSubsets"
ReportingEvent ||--}o DisplaySection : "globalDisplaySections"
ReportingEvent ||--}o AnalysisCategorization : "analysisCategorizations"
ReportingEvent ||--}o Analysis : "analyses"
ReportingEvent ||--}o Output : "outputs"
Output ||--}o File : "fileSpecifications"
Output ||--}o OutputDisplay : "outputDisplays"
Output ||--}o AnalysisCategory : "categoryRefs"
AnalysisCategory ||--}o AnalysisCategorization : "subCategorizations"
AnalysisCategorization ||--}| AnalysisCategory : "categories"
OutputDisplay ||--|o Display : "display"
Display ||--}o DisplaySection : "displaySections"
DisplaySection ||--}o DisplaySubSection : "subSections"
Analysis ||--}o AnalysisCategory : "categoryRefs"
Analysis ||--|o AnalysisSet : "analysisSetRef"
Analysis ||--}o OrderedGroupingFactor : "orderedGroupings"
Analysis ||--|o DataSubset : "dataSubsetRef"
Analysis ||--|o AnalysisMethod : "method"
AnalysisMethod ||--}| Operation : "operations"
Operation ||--}o ReferencedResultRelationship : "referencedResultRelationships"
Operation ||--}o OperationResult : "results"
OperationResult ||--}o AnalysisGroup : "groupRefs"
AnalysisGroup ||--|o Condition : "condition"
AnalysisGroup ||--|o CompoundGroupExpression : "compoundExpression"
CompoundGroupExpression ||--}o Group : "whereClauses"
Group ||--|o Condition : "condition"
Group ||--|o CompoundGroupExpression : "compoundExpression"
ReferencedResultRelationship ||--|| Operation : "operationRef"
DataSubset ||--|o Condition : "condition"
DataSubset ||--|o CompoundSubsetExpression : "compoundExpression"
CompoundSubsetExpression ||--}o WhereClause : "whereClauses"
WhereClause ||--|o Condition : "condition"
WhereClause ||--|o CompoundExpression : "compoundExpression"
CompoundExpression ||--}o WhereClause : "whereClauses"
OrderedGroupingFactor ||--|o GroupingFactor : "groupingRef"
OrderedGroupingFactor ||--|o DataGroupingFactor : "dataGrouping"
DataGroupingFactor ||--}o DataGroup : "groups"
DataGroup ||--|o Condition : "condition"
DataGroup ||--|o CompoundGroupExpression : "compoundExpression"
GroupingFactor ||--}o Group : "groups"
AnalysisSet ||--|o Condition : "condition"
AnalysisSet ||--|o CompoundSetExpression : "compoundExpression"
CompoundSetExpression ||--}o AnalysisSet : "whereClauses"
SubjectGroupingFactor ||--}o AnalysisGroup : "groups"
NestedList ||--}o OrderedListItem : "listItems"
OrderedListItem ||--|o NestedList : "sublist"
OrderedListItem ||--|o Analysis : "analysisRef"
OrderedListItem ||--|o Output : "outputRef"

```
