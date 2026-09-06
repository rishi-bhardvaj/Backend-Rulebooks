# Authorization

Authentication answers who the caller is; authorization answers what that identity may do.

Derive authorization from trusted server-side identity and server-side resource/tenant data. Never trust client-supplied userId, role, tenantId, permission, or ownership flags. Enforce authorization at every protected operation, not only at UI or route visibility.

Cover RBAC/permissions, object-level ownership, tenant isolation, admin boundaries, and privilege escalation. Mandatory negative test for resource access: User A token → User B private resource → deny (403 or intentionally indistinguishable 404 according to policy). Also test lower-privilege → admin action and cross-tenant access.