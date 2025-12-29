domino-issue-tracker/
├── README.md
├── .gitignore
├── .domino-project.json
├── .github/
│   └── workflows/
│       └── ci.yml
├── source/
│   ├── forms/
│   │   ├── IssueForm.dxl
│   │   ├── CommentForm.dxl
│   │   └── AuditLog.dxl
│   ├── views/
│   │   ├── AllIssues.dxl
│   │   ├── ByStatus.dxl
│   │   ├── MyWorkQueue.dxl
│   │   └── AttachmentsByIssue.dxl
│   ├── agents/
│   │   ├── CreateIssueAgent.lss
│   │   ├── SLAUpdater.lss
│   │   ├── NotifyOnAssignment.lss
│   │   ├── LogFieldChanges.lss
│   │   ├── GetIssues.lss
│   │   ├── PostIssue.lss
│   │   └── AttachmentManager.lss
│   └── scriptlibraries/
│       └── ls/
│           ├── IssueUtils.lss
│           ├── SLAUtils.lss
│           └── NotificationUtils.lss
├── tools/
│   ├── export-dxl.sh
│   └── import-dxl.sh
├── build/
│   └── .placeholder
└── docs/
    ├── architecture.md
    └── import_instructions.md
