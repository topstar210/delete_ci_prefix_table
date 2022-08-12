# delete_ci_prefix_table
This query is for deleting the table with prefix


$rs = $this->db->query('Show Tables')->result_array();
foreach ($rs as $key => $tb) {
    $tbname = $tb['Tables_in_' . APP_DB_NAME];
    $TF = strpos($tbname, $prefix);
    if ($TF === 0) {
        $this->db->query("SET FOREIGN_KEY_CHECKS = 0;");
        $this->db->query("drop table " . $tbname);
    }
}
