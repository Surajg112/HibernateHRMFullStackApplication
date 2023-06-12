# HibernateHRMFullStackApplication
----------------------------------------------------------------------------------
find by date ---->

getdatabyDOB("09-09-2021");

static void getdataByDOB(String uiDOB) {
		Session session = factory.openSession();
		SimpleDateFormat simpleDateFormat = new SimpleDateFormat("dd-MM-yyyy");
		
		List<Employee> employees = session.createQuery("from Employee").list();
		
		List<Employee> empList = new ArrayList<>();
		for(Employee employee: employees) {
			String dbDOBDate = simpleDateFormat.format(employee.getEmpDOB());
			if(uiDOB.equals(dbDOBDate)) {
				empList.add(employee);
			}	
		}
		empList.forEach(System.out::println);
		
	}
  
