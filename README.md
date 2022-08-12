# delete_ci_prefix_table
This query is for deleting the table with prefix


$rs = $this->db->query('Show Tables')->result_array();  <br />
foreach ($rs as $key => $tb) {                   <br />
    $tbname = $tb['Tables_in_' . APP_DB_NAME];    <br />
    $TF = strpos($tbname, $prefix);<br />
    if ($TF === 0) {<br />
        $this->db->query("SET FOREIGN_KEY_CHECKS = 0;");<br />
        $this->db->query("drop table " . $tbname);<br />
    }<br />
}<br />
