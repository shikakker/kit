# Completion plan

1. Establish provenance first: `kit` appears to be a substantial Next.js conference/video-event starter with 100ms (`hms`) room components, conference entries, contact/form/captcha and extensive environment configuration. Document upstream/template origin and the modifications actually owned here.
2. Inventory every variable in `.env.local.example` by service and privilege. Server secrets stay server-only; browser-exposed IDs/tokens must be intentionally public/scoped. Remove obsolete provider variables rather than encouraging users to configure unused integrations.
3. Trace the complete 100ms room lifecycle: join/token acquisition, camera/mic permissions, active speaker, screenshare, pagination, settings and leave. Tokens must be generated server-side with bounded role/room access and expiry.
4. Add explicit camera/microphone/screen-sharing consent and robust denied/revoked/device-missing states. Never start capture before a clear user action and visibly indicate active media/screen sharing.
5. Harden public forms/contact/captcha: server-side validation, spam/rate protection, safe error handling and privacy disclosure for submitted attendee/contact data. Do not trust captcha success from the client alone.
6. Define conference data semantics in `conf-entry`/container flows: schedule/timezone, capacity, join eligibility and live/ended states. Do not display a session as live solely from static fixture dates.
7. Improve video-room resilience: reconnect state, participant churn, device changes, track subscription limits, screenshare conflicts and clean resource teardown when leaving/navigating.
8. Audit accessibility and responsive behavior for conference listings and room controls: keyboard/focus, aria labels, visible mic/camera state, captions/transcript hooks if supported and non-video fallback for users without devices.
9. Add mocked token/form tests and 100ms interaction tests for join/leave/permissions/reconnect/screenshare; CI runs lint/typecheck/tests and Next.js production build without production service secrets.
10. Rewrite README as verified video-event starter/prototype documentation: provenance, actual integrations, conference/room flow, permission/privacy model, env setup, screenshots and limitations versus a production webinar platform.
