
Functional Requirements Document (FRD)
Project: AwesomeCMMS (Computerized Maintenance Management System)
Version: 1.0 (System Functionality) / 1.1 (FRD Document - UI Enhanced)
Document Version: 1.1
Date: October 27, 2023 (User to replace with actual current date)
Based on: System Documentation: AwesomeCMMS Version 1.0 (CMMS.txt) & Provided UI Mockup Images.
1. Introduction
* 1.1. Purpose: This document specifies the functional requirements for the AwesomeCMMS Version 1.0. The AwesomeCMMS is designed to manage and track equipment assets, maintenance activities, work orders, spare parts, and associated data to improve asset reliability, streamline maintenance operations, and provide insights into maintenance performance. This FRD is intended to be used by development teams, including AI programming agents, to guide the implementation of the system, particularly its Power Apps user interface.
* 1.2. Scope:
o In Scope (Version 1.0 Foundation):
* Equipment registry and asset information management.
* Work order creation, assignment, and status tracking.
* Maintenance history logging for equipment.
* Technician information management.
* Basic spare parts inventory tracking.
* Tracking parts used on work orders.
* Standardized failure code logging and analysis.
* User interface implemented in Power Apps, with specific layouts based on provided mockups.
o Out of Scope (Version 1.0 - Future Enhancements as per CMMS.txt):
* Advanced automation for PM generation (mechanism TBD).
* Detailed operational logging for MTBF/MTTR (conceptual).
* Direct data integration points or shared workflows with Customer Order & Production Tracking System (can be explored later).
* Dedicated CMMS_Users table with integrated authentication (user identification currently via VARCHAR fields or CMMS_Technicians).
* Advanced mobile features beyond standard Power Apps mobile-friendliness (e.g., specific offline capabilities).
* Reporting Dashboards (conceptual, to be built later).
* 1.3. Document Conventions:
o Requirements are identified with a unique ID (e.g., FR-EQ-001, FR-UI-S01.1).
o References to the System Documentation (CMMS.txt) will be made where applicable (e.g., Section 3: CMMS_Equipment).
o UI layout requirements reference provided image mockups.
* 1.4. Target Audience (of the FRD): Software developers, AI programming agents (specifically for Power Apps YAML generation), QA testers, project managers.
* 1.5. Target Audience (of the AwesomeCMMS System): Maintenance Managers, Maintenance Technicians, Plant Engineers, Storeroom Personnel, (potentially) Plant Managers, and individuals requesting maintenance. (Ref: CMMS.txt Section 2).
2. System Overview (Recap)
The AwesomeCMMS (Computerized Maintenance Management System) is designed to manage and track equipment assets, maintenance activities, work orders, spare parts, and associated data to improve asset reliability, streamline maintenance operations, and provide insights into maintenance performance. Key functionalities include equipment registry, work order management, maintenance history, technician management, parts inventory, and failure code analysis.
3. User Roles & Personas (Anticipated - High Level)
(Ref: CMMS.txt Section 5)
The system must support functionalities tailored to the following roles:
* 3.1. Maintenance Technician:
o FR-UR-001: Ability to view work orders assigned to them.
o FR-UR-002: Ability to update the status of their assigned work orders.
o FR-UR-003: Ability to log labor hours (actual hours) against work orders.
o FR-UR-004: Ability to record parts used on work orders.
o FR-UR-005: Ability to add completion notes to work orders.
o FR-UR-006: Ability to view and update individual tasks within a work order.
* 3.2. Maintenance Supervisor/Manager:
o FR-UR-007: Ability to create new work orders.
o FR-UR-008: Ability to assign work orders to technicians.
o FR-UR-009: Ability to review completed work orders.
o FR-UR-010: Ability to manage (CRUD) equipment data.
o FR-UR-011: Ability to manage (CRUD) parts inventory.
o FR-UR-012: Ability to view system reports (placeholder for future reports).
* 3.3. Storeroom Clerk:
o FR-UR-013: Ability to manage (CRUD) parts inventory, specifically stock levels.
o FR-UR-014: Ability to record the issuance of parts for work orders.
* 3.4. Requester (General User):
o FR-UR-015: Ability to submit maintenance requests that may become work orders.
* 3.5. Administrator:
o FR-UR-016: Ability to manage (CRUD) system lookup lists (e.g., Failure Codes, Statuses, Priorities, Work Order Types).
4. Core Functional Requirements (Data Operations)
* 4.1. Module: Equipment Management (Interface for CMMS_Equipment & CMMS_EquipmentDocumentation)
o FR-EQ-001: Create New Equipment Record (Details as per FRD v1.0).
o FR-EQ-002: View Equipment List (Details as per FRD v1.0).
o FR-EQ-003: Search/Filter Equipment List (Details as per FRD v1.0).
o FR-EQ-004: View Equipment Details (Details as per FRD v1.0).
o FR-EQ-005: Edit Equipment Record (Details as per FRD v1.0).
o FR-EQ-006: Manage Equipment Documentation (FR-EQ-006.1: Add, FR-EQ-006.2: View - Details as per FRD v1.0).
* 4.2. Module: Work Order Management (Interface for CMMS_WorkOrders)
o FR-WO-001: Create New Work Order Record (Details as per FRD v1.0, including auto-generation of WorkOrderNumber).
o FR-WO-002: View Work Order List (Details as per FRD v1.0).
o FR-WO-003: Search/Filter Work Order List (Details as per FRD v1.0).
o FR-WO-004: View Work Order Details (Details as per FRD v1.0).
o FR-WO-005: Edit Work Order Record (Details as per FRD v1.0).
o FR-WO-006: Assign Technician to Work Order (Details as per FRD v1.0).
o FR-WO-007: Update Work Order Status (Details as per FRD v1.0).
o FR-WO-008: Log Actual Hours for Work Order (Details as per FRD v1.0).
o FR-WO-009: Record Completion Details (Details as per FRD v1.0).
o FR-WO-010: Link Failure Code to Work Order (Details as per FRD v1.0).
* 4.3. Module: Technician Management (Interface for CMMS_Technicians)
o FR-TECH-001: Create Technician Record (Details as per FRD v1.0).
o FR-TECH-002: View Technician List (Details as per FRD v1.0).
o FR-TECH-003: View Technician Details (Details as per FRD v1.0).
o FR-TECH-004: Edit Technician Record (Details as per FRD v1.0).
* 4.4. Module: Parts Management (Interface for CMMS_Parts)
o FR-PART-001: Create Part Record (Details as per FRD v1.0).
o FR-PART-002: View Parts List (Details as per FRD v1.0).
o FR-PART-003: View Part Details (Details as per FRD v1.0).
o FR-PART-004: Edit Part Record (Details as per FRD v1.0).
* 4.5. Module: Failure Code Management (Interface for CMMS_FailureCodes)
o FR-FC-001: Create Failure Code Record (Details as per FRD v1.0).
o FR-FC-002: View Failure Code List (Details as per FRD v1.0).
o FR-FC-003: View Failure Code Details (Details as per FRD v1.0).
o FR-FC-004: Edit Failure Code Record (Details as per FRD v1.0).
* 4.6. Module: Work Order Tasks Management (Interface for CMMS_WorkOrderTasks)
o FR-TASK-001: Add Task to Work Order (Details as per FRD v1.0).
o FR-TASK-002: View Tasks for a Work Order (Details as per FRD v1.0).
o FR-TASK-003: Update Task Status (Details as per FRD v1.0).
o FR-TASK-004: Edit Task Details (Details as per FRD v1.0).
o FR-TASK-005: Log Actual Hours for Task (Details as per FRD v1.0).
* 4.7. Module: Work Order Parts Used Management (Interface for CMMS_WorkOrderPartsUsed)
o FR-WOPU-001: Record Part Used on Work Order (Details as per FRD v1.0, including stock decrement).
o FR-WOPU-002: View Parts Used for a Work Order (Details as per FRD v1.0).
* 4.8. Module: Maintenance History (Interface for CMMS_MaintenanceHistory)
o FR-MH-001: Log Maintenance Activity (Details as per FRD v1.0).
o FR-MH-002: View Maintenance History for Equipment (Details as per FRD v1.0).
5. Data Requirements
(As per FRD Version 1.0 - Section 5, unchanged)
* 5.1. Data Sources: [AwesomeDatabase].[dbo] schema.
* 5.2. Core Tables: CMMS_Equipment, CMMS_EquipmentDocumentation, CMMS_Technicians, CMMS_WorkOrders, CMMS_FailureCodes, CMMS_MaintenanceHistory, CMMS_WorkOrderTasks, CMMS_Parts, CMMS_WorkOrderPartsUsed.
* 5.3. Data Integrity: PK, FK, CHECK, UNIQUE, NOT NULL constraints enforced.
* 5.4. Data Defaults: Database or application defaults applied as specified.
6. User Interface (UI) / User Experience (UX) Functional Requirements (Layout Specifics)
This section details the layout and key interactive elements for specific screens, based on the provided UI mockup images. The target output for an AI programming agent building these Power Apps screens would be the corresponding Power Apps YAML source code.
* FR-UI-S01: General Application Layout (Consistent Across Screens - Ref: All Images)
o FR-UI-S01.1: Main Navigation: A persistent left-hand vertical navigation panel shall be present (approx. width 250-280px).
* Controls: Vertical Gallery or series of Buttons/Icons for navigation items (e.g., App Branding Label like "Acme Co", Icon+Label for "Dashboard," "Assets," "Work Orders," "Parts," "Reports").
* Behavior: Clicking a navigation item shall navigate to the respective screen. The currently active section (e.g., "Work Orders") shall be visually highlighted (e.g., background color change, font weight change, accent border).
o FR-UI-S01.2: Top Bar (Conceptual - Ref: Work Orders list image top right): A horizontal bar above the main content area.
* Controls (Example): May contain a global search Text Input, a notification Icon, and a user profile Icon/Image. (Exact implementation flexible for V1.0).
o FR-UI-S01.3: Content Area: The area to the right of the left navigation panel is the main content display area for the selected screen, typically with padding.
* FR-UI-S02: Equipment Assets List Screen (Ref: Equipment Assets Image)
o Screen Name (Suggested Power Apps): scrEquipmentList
o FR-UI-S02.1: Header Section:
* Title: Label displaying "Equipment Assets" (large font, bold).
* Action Button: Button labeled "Add Asset" positioned top-right of the content area.
* OnSelect: Navigate to scrAddEditEquipment (or a dedicated equipment form screen) with its form (e.g., formEquipment) in NewForm mode.
o FR-UI-S02.2: Search Bar:
* Control: Text Input, positioned below the header.
* Placeholder Text: "Search assets by ID, location, or status".
* Behavior: Text entered shall filter galEquipmentList. Clear button should be visible.
o FR-UI-S02.3: Equipment List Gallery:
* Control: Vertical Gallery (galEquipmentList).
* DataSource: CMMS_Equipment.
* Items Filtering: Filtered by the Search Bar (FR-UI-S02.2) on CMMS_Equipment fields: EquipmentAssetTag, Location, Status.
* Layout: Tabular. Column header Labels above the gallery: "Asset ID", "Status", "Location", "Next Maintenance", "Last Updated".
* Gallery Row Template (Each row representing one equipment item):
* Asset ID: Label displaying ThisItem.EquipmentAssetTag.
* Status: Label displaying ThisItem.Status.
* Styling: Text centered within a rounded rectangle ("pill" shape). Background fill color of the pill dynamically changes based on ThisItem.Status values (e.g., "Operational": light green/blue, "Under Maintenance": light yellow/orange. Refer to CMMS_Equipment.Status CHECK constraint for all values).
* Location: Label displaying ThisItem.Location.
* Next Maintenance: Label displaying Text(ThisItem.NextMaintenanceDate, "yyyy-mm-dd").
* Last Updated: Label displaying Text(ThisItem.LastUpdatedDate, "yyyy-mm-dd").
* Row Separator: Light horizontal line between items.
* Behavior: Selecting a row (item) in the gallery shall navigate to scrAddEditEquipment (or dedicated equipment form screen) with its form set to EditForm mode and Item property set to Self.Selected.
* FR-UI-S03: Work Orders List Screen (Ref: Work Orders List Image)
o Screen Name (Suggested Power Apps): scrWorkOrderList
o FR-UI-S03.1: Header Section:
* Title: Label displaying "Work Orders" (large font, bold).
* Action Button: Button labeled "New Work Order" positioned top-right of the content area.
* OnSelect:
1. Execute Power Fx logic to determine and set a global variable (e.g., gblNewWorkOrderNumber) for the auto-generated WorkOrderNumber (as per FR-WO-001).
2. Call NewForm() on the work order form (e.g., formWorkOrder on scrWorkOrderForm).
3. Navigate to scrWorkOrderForm.
o FR-UI-S03.2: Search Bar:
* Control: Text Input, positioned below the header.
* Placeholder Text: "Search work orders...".
* Behavior: Text entered shall filter galWorkOrderList. Clear button should be visible.
o FR-UI-S03.3: Work Order List Gallery:
* Control: Vertical Gallery (galWorkOrderList).
* DataSource: CMMS_WorkOrders.
* Items Filtering: Filtered by the Search Bar (FR-UI-S03.2) on CMMS_WorkOrders fields: WorkOrderNumber, Title. (Advanced: consider filtering by looked-up values like equipment name if performance allows).
* Layout: Tabular. Column header Labels above the gallery: "ID", "Equipment", "Status", "Due Date", "Assigned Technician".
* Gallery Row Template (Each row representing one work order):
* ID: Label displaying ThisItem.WorkOrderNumber.
* Equipment: Label displaying LookUp(CMMS_Equipment, EquipmentID = ThisItem.EquipmentID).EquipmentName.
* Status: Label displaying ThisItem.Status.
* Styling: Text centered within a rounded rectangle ("pill" shape). Background fill color dynamically changes based on ThisItem.Status values (e.g., "Open": light blue, "In Progress": light orange, "Completed": light green. Refer to CMMS_WorkOrders.Status CHECK constraint).
* Due Date: Label displaying Text(ThisItem.DueDate, "yyyy-mm-dd").
* Assigned Technician: Label displaying If(IsBlank(ThisItem.AssignedTechnicianID), "Unassigned", LookUp(CMMS_Technicians, TechnicianID = ThisItem.AssignedTechnicianID).TechnicianName).
* Row Separator: Light horizontal line between items.
* Behavior: Selecting a row (item) in the gallery shall navigate to scrWorkOrderView (the Work Order View/Details screen) with the Item context set to Self.Selected.
* FR-UI-S04: Work Order Form Screen (Create/Edit - Ref: Previous YAML for scrAddEditWorkOrder)
o Screen Name (Suggested Power Apps): scrWorkOrderForm (This screen is dedicated to the form for creating/editing WOs).
o FR-UI-S04.1: Form Control:
* Control: Edit Form (formWorkOrder).
* DataSource: CMMS_WorkOrders.
* Item (for Edit Mode): Populated by the selected item from galWorkOrderList when navigating for an edit.
* Layout: Vertical, 2 columns typically.
* Fields (Data Cards - key examples, refer to detailed YAML for full list and specific control properties):
* WorkOrderNumber (Text Input): Default set to gblNewWorkOrderNumber when formWorkOrder.Mode = FormMode.New. DisplayMode set to DisplayMode.View when formWorkOrder.Mode = FormMode.New. (Required, Unique handled by DB).
* EquipmentID (ComboBox): Items from CMMS_Equipment. Displays EquipmentName, stores EquipmentID. (Required). DefaultSelectedItems based on Parent.Default for edit.
* Title (Text Input): (Required).
* Description (Text Input, Mode: MultiLine).
* Status (Dropdown): Items from CMMS_WorkOrders.Status CHECK constraint. Default "Open" for new. (Required).
* Priority (Dropdown): Items from CMMS_WorkOrders.Priority CHECK constraint. Default "Medium" for new. (Required).
* WorkOrderType (Dropdown): Items from CMMS_WorkOrders.WorkOrderType CHECK constraint. (Required).
* RequestedBy (Text Input): Default User().FullName for new. DisplayMode.View for new.
* RequesterEmail (Text Input): Default User().Email for new. DisplayMode.View for new.
* DateRequested (Date Picker): Default Now() for new. (Required). Time component may be hidden if only date is needed, but Now() captures time.
* AssignedTechnicianID (ComboBox): Items from active CMMS_Technicians. Displays TechnicianName, stores TechnicianID. DefaultSelectedItems for edit.
* FailureCodeID (ComboBox): Items from active CMMS_FailureCodes. Displays Description or Code, stores FailureCodeID. DefaultSelectedItems for edit.
* CreatedDate, LastUpdatedDate: DataCards set to DisplayMode.View. Default properties show ThisItem.CreatedDate/ThisItem.LastUpdatedDate. Update properties set to Blank() for CreatedDate (DB default) and Now() for LastUpdatedDate on edit.
o FR-UI-S04.2: Action Buttons:
* "Save Work Order" Button: OnSelect: SubmitForm(formWorkOrder).
* "Back" / "Cancel" Button: OnSelect: ResetForm(formWorkOrder); Back().
o FR-UI-S04.3: Form Behavior:
* OnSuccess: Notify user of success, ResetForm(formWorkOrder), and navigate Back().
* OnFailure: Notify user of error.
* FR-UI-S05: Work Order View/Details Screen (Ref: WO-2023-0012 Details Image)
o Screen Name (Suggested Power Apps): scrWorkOrderView
o OnVisible Behavior:
1. Set(varCurrentWO, galWorkOrderList.Selected) (or retrieve WO based on passed ID).
2. If(IsBlank(varCurrentWO.WorkOrderID), Navigate(scrWorkOrderList, ScreenTransition.None)) (handle case where WO not found).
3. UpdateContext({ctlSelectedTab: "Details"}) (set default tab).
o FR-UI-S05.1: Header Section:
* Breadcrumbs Label: Text: "Work Orders / " & varCurrentWO.WorkOrderNumber.
* Work Order Number Label: Text: varCurrentWO.WorkOrderNumber (large, bold font).
* Scheduled Date Sub-Header Label: Text: "Scheduled for " & Text(varCurrentWO.ScheduledStartDate, "MM/dd/yyyy") (or DueDate).
o FR-UI-S05.2: Tab Navigation Controls:
* Controls: Three Button controls labeled "Details", "Tasks", "Materials".
* Behavior: OnSelect of each button updates ctlSelectedTab context variable to "Details", "Tasks", or "Materials" respectively. Active tab visually distinct (e.g., different fill/color, underline).
o FR-UI-S05.3: "Details" Tab Content Area (Visible when ctlSelectedTab = "Details"):
* Container to hold all detail elements.
* Section Title Label: "Work Order Details".
* Layout: Information displayed as pairs of Labels: one for the field name (e.g., "Status") and one for its value (e.g., varCurrentWO.Status). Arranged logically, potentially in a two-column gallery or using individual labels positioned in two columns.
* Status: Label: "Status", Value Label: varCurrentWO.Status.
* Priority: Label: "Priority", Value Label: varCurrentWO.Priority.
* Assigned To: Label: "Assigned To", Value Label: LookUp(CMMS_Technicians, TechnicianID = varCurrentWO.AssignedTechnicianID).TechnicianName.
* Equipment: Label: "Equipment", Value Label: LookUp(CMMS_Equipment, EquipmentID = varCurrentWO.EquipmentID).EquipmentName.
* Location: Label: "Location", Value Label: Coalesce(varCurrentWO.LocationOverride, LookUp(CMMS_Equipment, EquipmentID = varCurrentWO.EquipmentID).Location).
* Requested By: Label: "Requested By", Value Label: varCurrentWO.RequestedBy.
* Description: Label: "Description", Value Label: varCurrentWO.Description (ensure wrap for long text).
* Notes (Completion Notes): Label: "Notes", Value Label: varCurrentWO.CompletionNotes (ensure wrap).
* Section Title Label: "Time Tracking".
* Start Time: Label: "Start Time", Value Label: Text(varCurrentWO.ActualStartDate, "mm/dd/yyyy hh:mm AM/PM").
* End Time: Label: "End Time", Value Label: Text(varCurrentWO.ActualEndDate, "mm/dd/yyyy hh:mm AM/PM").
* Total Time: Label: "Total Time", Value Label: varCurrentWO.ActualHours & " hours".
* Technician (Performed By): Label: "Technician", Value Label: LookUp(CMMS_Technicians, TechnicianID = varCurrentWO.AssignedTechnicianID).TechnicianName (or a specific PerformedByTechnicianID if different).
o FR-UI-S05.4: "Tasks" Tab Content Area (Visible when ctlSelectedTab = "Tasks"):
* Shall display a list/gallery of tasks from CMMS_WorkOrderTasks related to varCurrentWO.WorkOrderID.
* Provide ability to view/manage tasks (could navigate to scrWorkOrderTasks or embed functionality).
o FR-UI-S05.5: "Materials" Tab Content Area (Visible when ctlSelectedTab = "Materials"):
* Shall display a list/gallery of parts used from CMMS_WorkOrderPartsUsed related to varCurrentWO.WorkOrderID.
* Provide ability to view/manage parts used (could navigate to scrWorkOrderPartsUsed or embed functionality).
o FR-UI-S05.6: Action Button Area (Positioned bottom-right of content area):
* "Complete Work Order" Button:
* Visible: =varCurrentWO.Status <> "Completed".
* OnSelect:
1. (Optional: If fields like ActualHours, CompletionNotes are not directly editable on this view, show a pop-up/modal form to collect these values before patching).
2. Patch(CMMS_WorkOrders, varCurrentWO, {Status: "Completed", ActualEndDate: Now() /*, ActualHours: capturedActualHours, CompletionNotes: capturedCompletionNotes */}).
3. Notify user of success.
4. Refresh varCurrentWO: Set(varCurrentWO, LookUp(CMMS_WorkOrders, WorkOrderID = varCurrentWO.WorkOrderID)).
* (Optional) "Edit Work Order" Button:
* Visible: =varCurrentWO.Status <> "Completed".
* OnSelect: Navigate(scrWorkOrderForm, ScreenTransition.None, {WorkOrderItem: varCurrentWO}) (and formWorkOrder.Item on scrWorkOrderForm would use WorkOrderItem). The form should then be in EditForm mode.
* FR-UI-S06: Work Order Tasks Screen (scrWorkOrderTasks - If separate screen)
o OnVisible: Set(currentWO_ID, PassedInWorkOrderID). Filter CMMS_WorkOrderTasks where WorkOrderID = currentWO_ID.
o Layout: Gallery displaying task Sequence, TaskDescription, Status, EstimatedHours, ActualHours.
o Functionality: Allow adding new tasks, editing existing tasks, changing task status (e.g., via a dropdown in the gallery), logging actual hours per task. (Ref: FR-TASK-XXX).
* FR-UI-S07: Work Order Parts Used Screen (scrWorkOrderPartsUsed - If separate screen)
o OnVisible: Set(currentWO_ID, PassedInWorkOrderID). Filter CMMS_WorkOrderPartsUsed where WorkOrderID = currentWO_ID.
o Layout: Gallery displaying PartName (lookup from CMMS_Parts), QuantityUsed, UnitPriceAtTimeOfUse.
o Functionality: Button to "Add Part Used" which navigates to a form/popup. Form allows selecting a Part from CMMS_Parts (ComboBox), entering QuantityUsed. On save, creates record in CMMS_WorkOrderPartsUsed and updates CMMS_Parts.StockQuantity. (Ref: FR-WOPU-XXX).
7. Non-Functional Requirements (High Level for V1.0)
(As per FRD Version 1.0 - Section 7, unchanged)
* FR-NFR-001: Performance.
* FR-NFR-002: Usability.
* FR-NFR-003: Reliability.
* FR-NFR-004: Data Accuracy.
8. Assumptions and Constraints
(As per FRD Version 1.0 - Section 8, unchanged)
* AC-001: Accuracy of the CMMS relies on timely and accurate data entry.
* AC-002: Initial version may rely on manual processes.
* AC-003: User identification via VARCHAR fields in V1.0.
9. Acceptance Criteria (Examples - To be expanded per requirement)
(As per FRD Version 1.0 - Section 9, but would be expanded to include UI specific checks like:)
* AC-UI-S03.3 (for FR-UI-S03.3): The Work Orders list screen displays a gallery with columns for ID, Equipment, Status, Due Date, and Assigned Technician. The Status field is displayed as a colored pill corresponding to the status value.
* AC-UI-S05.3 (for FR-UI-S05.3): When the "Details" tab is selected on the Work Order View screen, all specified fields (Status, Priority, Equipment, etc.) are displayed with their correct values from the current work order record (varCurrentWO).

