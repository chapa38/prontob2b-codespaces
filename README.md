## ProntoB2B Codespaces Stack
Levanta Mautic 6.0.5 + MariaDB 10.6 + n8n + Postgres 16 + MailHog.

### Pasos rápidos
1) Copiá `.env.example` a `.env` y completá credenciales de **dev** (no producción).
2) Abrí en Codespaces (este repo ya trae `.devcontainer`).
3) Puertos:
   - Mautic → 8080
   - n8n → 5678
   - MailHog → 8025

### Importar datos (opcional)
- Mautic DB: `gunzip -c /data-seed/mautic.sql.gz | mysql -h mautic-db -u$MAUTIC_DB_USER -p$MAUTIC_DB_PASSWORD $MAUTIC_DB_NAME`
- n8n DB: `pg_restore -U $N8N_DB_USER -d $N8N_DB_NAME /data-seed/n8n.dump`
- Media/var: `tar -xzf /data-seed/mautic_media_var.tar.gz -C /var/www/html`
