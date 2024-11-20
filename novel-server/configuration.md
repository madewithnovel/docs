# Configuration

```javascript
export default {
	app: {
		host: process.env.HOST || 'http://localhost:7634',
		secure: true,
		cors: {
			origin: true,
		},
		notify_webhook: process.env.NOTIFY_WEBHOOK,
		devtools: true, // show the devtool in the UI

		achievements: false, // some hooks to show notification locally for some milestones on the dev journey
		checklist: false, // go through the checklist before deploying
		// root_key: process.env.APP_ROOT_KEY,
		// name: 'Novel',
		// allowed_hostnames: '*',
		// https: process.env.NODE_ENV === 'production',
		// docs: true,
		// admin: true,
		// secrets: {
		// 	driver: 'default',
		// },
		// session: {
		// 	secret: process.env.SESSION_SECRET,
		// 	lifetime: 'browser', // or ms format. like 7 days
		// 	expire_on_close: false,
		// },
		// logger: {
		// 	enabled: true,
		// 	level: 'info',
		// },
		// telemetry: {
		// 	driver: 'sentry',
		// 	credentials: {
		// 		dsn: process.env.SENTRY_DSN,
		// 	},
		// },
		telemetry: true, // enables telemetry for packages/novel
	},
	auth: {
		mfa: true,
		register_on_oauth: false,
		allow_unverified: false,
		verification_expiry: '3d',
		routes: {
			login: '/login',
			mfa: '/login/mfa',
			link: '/login/link',
			forget: '/login/forget',
			verify: '/mail/verify',
			signup: '/signup',
			after_login: '/dashboard',
			logout: '/logout',
		},
		roles: {
			superuser: ['all', 'admin'],
			admin: ['read', 'write', 'delete'],
			user: ['read', 'write'],
		},
	},
	// cache: {
	// 	driver: 'postgres',
	// 	prefix: null,
	// 	table: 'cache',
	// },
	database: {
		driver: 'postgres',
		connection: process.env.DB_HOST,
		cloudsql: {
			enabled: false,
			tables: [],
		},
	},
	filesystem: {
		driver: 's3',
		public_url: process.env.FILESYSTEM_PUBLIC_URL,
		default_bucket: process.env.FILESYSTEM_DEFAULT_BUCKET,
		credentials: {
			endpoint: process.env.FILESYSTEM_ENDPOINT,
			client_id: process.env.FILESYSTEM_ACCESS_KEY_ID,
			secret_key: process.env.FILESYSTEM_SECRET_ACCESS_KEY,
		},
		types: ['image', 'audio', 'video', 'application/pdf', 'application/vnd.', 'text'],
	},
	mail: {
		driver: 'postmark',
		credentials: {
			token: process.env.POSTMARK_SERVER_TOKEN,
			host: process.env.SMTP_HOST,
		},
		defaults: {
			from: process.env.DEFAULT_MAIL_FROM,
		},
	},
	// push: {
	// 	driver: 'vapid',
	// 	credentials: {
	// 		public_key: process.env.VAPID_PUBLIC_KEY,
	// 		private_key: process.env.VAPID_PRIVATE_KEY,
	// 	},
	// },
	saas: {
		driver: 'stripe',
		credentials: {
			token: process.env.STRIPE_API_TOKEN,
			webhook: process.env.STRIPE_WEBHOOK_SECRET,
		},
		sync: true,
		archive_on_remote: true,
		tax_included: false,
		currencies: ['USD'],
		aggregate_usage: 'sum',
		upfront: false,
		plans: [],
	},
	// scheduler: {
	// 	driver: 'database',
	// },
	// socket: {
	// 	driver: 'default',
	// 	enabled: true,
	// },
	// gpt: {
	// 	driver: 'openapi',
	// 	credentials: {
	// 		api_key: process.env.OPENAPI_API_KEY,
	// 	},
	// },
	defaults: {
		initial_settings: {
			theme: 'auto',
			timezone: 'UTC',
			language: 'en-US',
		},
		credits: {},
		quotas: {},
		limits: {
			global: {},
			user: {},
		},
	},
};

```

