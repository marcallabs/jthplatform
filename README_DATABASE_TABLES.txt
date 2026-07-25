The Admin Settings framework creates its database tables automatically through the existing jth_db() connection.

Tables:
- jth_settings_values
- jth_settings_list_items
- jth_settings_audit
- jth_settings_versions

If table creation is blocked by database permissions, copy the CREATE TABLE statements from /includes/settings-service.php into phpMyAdmin and run them once.
