# SmartReminder-Pro
SaaS multi-tenant WhatsApp + CRM + Faturamento
SmartReminder-Pro/
├── README.md                           # Complete documentation
├── .env.example                        # Environment variables template
├── docker-compose.yml                  # Docker orchestration
│
├── backend/
│   ├── database/
│   │   └── init.sql                   # Complete PostgreSQL schema with RLS
│   ├── supabase/
│   │   └── rls-policies.sql           # Multi-tenant Row Level Security
│   └── edge-functions/
│       ├── auth/signup.ts              # User registration
│       ├── whatsapp/webhook.ts         # WhatsApp inbound messages
│       ├── billing/pix-generator.ts    # PIX key generation
│       └── automations/trigger.ts      # Automation engine
│
├── frontend/
│   ├── package.json
│   ├── tsconfig.json
│   ├── next.config.js
│   ├── tailwind.config.ts
│   ├── postcss.config.js
│   ├── src/
│   │   ├── app/
│   │   │   ├── layout.tsx              # App layout with theme toggle
│   │   │   ├── auth/
│   │   │   │   ├── login/page.tsx
│   │   │   │   └── signup/page.tsx
│   │   │   ├── dashboard/page.tsx      # Main dashboard
│   │   │   ├── crm/
│   │   │   │   ├── page.tsx
│   │   │   │   ├── [id]/page.tsx
│   │   │   │   └── components/
│   │   │   ├── billing/
│   │   │   │   ├── page.tsx
│   │   │   │   ├── invoices/
│   │   │   │   └── payments/
│   │   │   ├── scheduling/
│   │   │   │   ├── page.tsx
│   │   │   │   └── calendar/
│   │   │   ├── automations/
│   │   │   │   ├── page.tsx
│   │   │   │   ├── [id]/page.tsx
│   │   │   │   └── builder/
│   │   │   ├── templates/
│   │   │   │   ├── page.tsx
│   │   │   │   └── editor/
│   │   │   └── admin/
│   │   │       ├── page.tsx
│   │   │       ├── tenants/
│   │   │       ├── analytics/
│   │   │       └── settings/
│   │   ├── components/
│   │   │   ├── ui/                    # shadcn/ui components
│   │   │   ├── layout/
│   │   │   ├── forms/
│   │   │   └── charts/
│   │   ├── lib/
│   │   │   ├── supabase.ts            # Supabase client
│   │   │   ├── api-client.ts
│   │   │   └── utils.ts
│   │   ├── hooks/
│   │   │   ├── useAuth.ts
│   │   │   ├── useTenant.ts
│   │   │   └── useTheme.ts
│   │   ├── types/
│   │   │   ├── index.ts
│   │   │   ├── supabase.ts
│   │   │   └── api.ts
│   │   └── stores/                    # Zustand stores
│   │       ├── authStore.ts
│   │       └── themeStore.ts
│
├── n8n/
│   ├── docker-compose.yml             # n8n setup
│   ├── workflows/
│   │   ├── invoice-created.json
│   │   ├── payment-received.json
│   │   ├── appointment-reminder.json
│   │   ├── customer-onboarding.json
│   │   └── overdue-payment-reminder.json
│   └── credentials/
│       ├── supabase.json
│       ├── whatsapp.json
│       └── mercado-pago.json
│
├── docs/
│   ├── ARCHITECTURE.md
│   ├── SETUP.md
│   ├── API.md
│   ├── DATABASE.md
│   ├── WHATSAPP.md
│   ├── AUTOMATION.md
│   ├── DEPLOYMENT.md
│   └── LGPD.md
│
└── scripts/
    ├── setup.sh
    ├── seed-data.sql
    └── deploy.sh