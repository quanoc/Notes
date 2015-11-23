###Spring��������
������һϵ�б��붼�ɹ��Ĳ�����ֻ��һ���ֲ���ʧ�ܣ����������Ĳ��轫Ҫ����������ع���

####��������ԣ�ACID��
- 1��ԭ����

�����ִ�й����У���������Ϊһ��������Ԫ������һ��������Ԫ��������������裬ÿ���������趼��ɲ����������

- 2��һ����

��֤���ݴ���һ��״̬������ʼ�ͽ����������Ҫ����һ��״̬����������ɹ���������ʧ�ܣ�

- 3��������

��֤������ʵ��κ����ݲ��������������������κθı��Ӱ�죬ֱ����������ɡ��������̵߳�ͬ���ԣ�

- 4���־���

��֤��������ִ�гɹ���������ϵͳ�в����Ľ���ǳ־õġ�

�����ύ������Դ��Ӧ�ó���֮���һ��Э�飬��������־�������Э��������¼.

��Ϊ��Ҫ���ǣ��ı䱾�����ǳ־õģ���һ������ܻ��ڴ˺�ı����ݡ���������־���ṩ��׷�������

�������ȡ������ӣ���������Ϊҵ���߼��Ĵ�����������Ҫ�������ǰ��״̬�������ʹ�����ݿ��������־��

�ܽ᣺���ı��������ԭ���Ա�ʾ�����Ƿ���ɣ�һ���Ա�ʾ������ִ��ʧ��ʱ�����и�����Ӱ������ݶ�Ӧ�ûָ�������ִ��ǰ��״̬��
�����Ա�ʾ����ִ�й����ж����ݵ��޸�,�������ύ֮ǰ�����������ǲ��ɼ��ģ��־��Ա�ʾ�Զ����ݵĲ���Ӧ���ǳ־õ�,��Ҳ�ǿ��Իָ���.

####��������3�ַ�ʽ

1����ϵ�����ݿ��������

���ݿ��ṩ���������������ݿ��У����������Ϊ3�����裺
````java
Begin Transaction(����������)
//����������
Commit��RollBack(�ύ��ع�)
End Transaction(�ύ������)
~~~~

˵��:����ĸ��뼶��ʹ��Isolation��ʾ��

- read uncommitted��������ȡ�κ��ύ��δ�ύ�ļ�¼�������ܼ�¼�Ƿ��ύ��������ȡ
- read committed��ֻ������ȡ�Ѿ��ύ�ļ�¼��
- repeatable��ֻ�ܿ�������ʼʱ�̵����ݿ��һ�����գ�����ʼ����ĵ����м�¼�����ύδ�ύ���޷�����

��������ݿ�Ĭ�ϵĸ��뼶����read committed��

2����ͳ��JDBC������

JDBC���ݿ�ӿڣ��ṩ�˻������ݿ����ӽ����������Ĺ��ܡ�

һ������̣����Ȼ�ȡ����Դ��Ȼ���������Դ��ȡ���ݿ����ӣ������趨����ʼ��ִ����Ӧ�Ĳ��������ִ�гɹ��ύ��ִ��ʧ����ع���
````java
public class Helloworld{
	private DataSource dataSource ;
	//��ȡ����Դ
	public void satDataSource(DataSource dataSource){
		this.dataSource = dataSource ;
	}
	Connection conn = null ;
	Statement stmt = null ;
	try{
		//��ȡ���ݿ�����
		conn = dataSource.getConnection() ;
		//��ʼ��������
		conn.setAutoCommit(false) ;
		stmt = conn.createStatement() ;
		//ִ����Ӧ����
		stmt.executeUpdate("INSERT INTO hello VALUES(1,'gf','helloworld')") ;
		//ִ�гɹ����ύ
		conn.commit() ;
	}catch(SQLException e){
		if(conn!=null){
			try{
				//ִ�в��ɹ����ع�
				conn.rollback() ;
			}catch(SQLException ex){
				System.out.println(ex);
			}
		}
	}finally{
		//����stmt��Ϊ�գ���ر�stmt
		if(stmt!=null){
			try{
				stmt.close();
			}catch(SQLException ex){
				System.out.println(ex);
			}
		}
		if(conn!=null){
			try{
				conn.close();
			}catch(){}
		}
	}
}
~~~~

3���ֲ�ʽ������

�ֲ�ʽ��������Զ�����ݿ��������������

�ֲ�ʽ�����������ֲ��ڶ����Դ�ϣ��ж���������������

�������¼���������
- ���Ҫ��ͬһԭ�Ӳ�����������Դͨ�š��������ת�ˣ������˻���ũҵ���еģ�Ҫ���������н���ת�ˡ�
- ������Ҫ��ͬһԭ�Ӳ����в�����������ͬ����֮��ת�ˣ�Ҫô����ϵͳ�������ɹ���Ҫô������ʧ�ܡ�
- �ֲ�ʽ������Ҫ�����ͬ������������ĺ�����

####Spring��������
- 1�����ʽ������
- 2������ʽ������

Spring�е��������ǻ��ڶ�̬AOP����ʵ�֡�

Spring��������Ľӿ���org.springframework.transaction.PlatformtransactionManager.


�������𣺱��ʽ��������ȴ�ͳ��JDBC���˺ܴ�ĸĽ�����������Щ�鷳����ΪҪʵ�־���ķ�����Spring����ʽ�������ṩ������õĽ��������

��С������ϵͳ�У�ֻ�к��ٵ����������ʹ�ñ��ʽ�������ȽϺã�����Ǵ��͵�����ϵͳ���д����������������ʹ������ʽ�������ȽϺá��������ǵ�������������ҵ���߼����롣