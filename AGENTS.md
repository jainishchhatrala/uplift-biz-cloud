<!-- LOVABLE:BEGIN -->
> [!IMPORTANT]
> This project is connected to [Lovable](https://lovable.dev). Avoid rewriting
> published git history — force pushing, or rebasing/amending/squashing commits
> that are already pushed — as it rewrites history on Lovable's side and the
> user will likely lose their project history.
>
> Commits you push to the connected branch sync back to Lovable and show up in
> the editor, so keep the branch in a working state.
<!-- LOVABLE:END -->

- ERP UI lives in src/erp (ported JSX); all data access goes through src/erp/api.js — keeps the original screens unchanged while the backend moved to Lovable Cloud.
- Business rules from the old Python backend are enforced by RLS + has_perm()/my_role() SQL helpers; stock changes happen only via the inventory_transactions trigger.
- User accounts sign in with a login ID mapped to `<login_id>@aalidhra-erp.app`; user management runs through admin-checked server functions in src/lib/users.functions.ts.
