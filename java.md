# javaleerdatos

private void leerdatos() {
        String[] cabecera = {"nombre", "cantidad", "precio", "fechaCreacion", "fechaVencimiento"};
        String[][] datos = null;
        model = new DefaultTableModel(datos, cabecera);
        jtbDatos.setModel(model);
        try {
            Class.forName("com.mysql.jdbc.Driver");
        } catch (Exception e) {
            System.out.println("No se encontra");
        }
        String url = "jdbc:mysql://localhost:3306/mercado";
        String user = "root";
   
JUAN ESTEBAN PATINO QUINTERO11:28
        String password = "";
        Connection conn = null;
        try {
            conn = (Connection) (DriverManager.getConnection(url, user, password));
        } catch (Exception e) {
            System.out.println("Hubo un error con la conexion!" + e);
        }
        Statement stmt = null;
        ResultSet rs = null;
        try {
            stmt = (Statement) conn.createStatement();
            rs = stmt.executeQuery("SELECT * FROM productoperecedero");
            while (rs.next(
while (rs.next()) {
                //               String cc = String.valueOf(rs.getInt(1));
                String nombre = rs.getString(1);
                int cantidad = rs.getInt(2);
                int precio = rs.getInt(3);
                String fechaCreacion = (rs.getString(4));
                String fechaVencimiento = (rs.getString(5));
                String[] temp = {nombre, Integer.toString(cantidad), Integer.toString(precio), fechaCreacion, fechaVencimiento};
                mode
JUAN ESTEBAN PATINO QUINTERO11:30
            }
            conn.close();
        } catch (Exception ex) {
            System.out.println("Hubo un error realizando la consulta" + ex);
        }
    }
