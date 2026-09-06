# Authorization Checklist

- [ ] Protected operations identified
- [ ] Server derives identity from trusted authentication
- [ ] Server derives role/permission/tenant/ownership from trusted state
- [ ] RBAC/permission rules tested
- [ ] Object-level access tested
- [ ] Cross-user access denied
- [ ] Cross-tenant access denied
- [ ] Lower privilege cannot perform admin action
- [ ] Client-supplied userId/role/tenantId/permission is not trusted
- [ ] Denial behavior follows documented 403/404 policy