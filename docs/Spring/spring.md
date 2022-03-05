
# <center>4. Spring</center>
Spring��һ����ܣ���IOC���������ã������ǳ�����Bean���󣬲������˶���������������ڵĹ�����ʹ�������ļ���ע��ȷ�ʽ����Bean��Ϣ������������֮����Ҫ�������Bean����ת����BeanDefinition�����BeanDefinition�Ľ����ͼ��ز�����ʵ������ͨ�����䴴�����󣬺�����г�ʼ��������aware�ӿڣ�init-Method��BeanPostProcessor��

### @RestController �� @Controller
- ����ʹ�� @Controller ���� @ResponseBody�Ļ�һ������Ҫ����һ����ͼ�����������������ڱȽϴ�ͳ��Spring MVC ��Ӧ�ã���Ӧ��ǰ��˲�����������
- @ResponseBody ע��������ǽ� Controller �ķ������صĶ���ͨ���ʵ���ת����ת��Ϊָ���ĸ�ʽ֮��д�뵽HTTP ��Ӧ(Response)����� body �У�ͨ���������� JSON ���� XML ���ݣ����� JSON ���ݵ�����Ƚ϶ࡣ


### IoC & AOP
#### IoC �� Dependency Injection
IoC(Inverse of Control) ���Ʒ�ת��һ�����˼�룬��ԭ���ֶ���������Ŀ���Ȩ������Spring���������IoC ������ Spring ����ʵ�� IoC �����壬IoC ����ʵ���Ͼ��Ǹ�Map(key��value), Map �д�ŵ��Ǹ��ֶ���

����ע��: ������֮����໥������ϵ���� IoC �������������� IoC ����������Ե�ע�롣  
�����ܹ��ܴ�̶��ϼ�Ӧ�õĿ�������Ӧ�ôӸ��ӵ�������ϵ�н�ų����� IoC ������һ����������������Ҫ����һ�������ʱ��ֻ��Ҫ���ú������ļ�/ע�⼴�ɣ���ȫ���ÿ��Ƕ�������α����������ġ� ��ʵ����Ŀ��һ�� Service ������м���������ǧ������Ϊ���ĵײ㣬����������Ҫʵ������� Service�������Ҫÿ�ζ�Ҫ������� Service ���еײ���Ĺ��캯����������� IoC �Ļ�����ֻ��Ҫ���úã�Ȼ������Ҫ�ĵط����þ����ˣ�������������Ŀ�Ŀ�ά�����ҽ����˿����Ѷȡ�


#### IoC�����ĳ�ʼ������
����ʱ��ȡBean������Դ��Ϣ��������BeanDefinition������Spring����������һ����Ӧ��Bean����ע�������ע���ʵ����Bean��Bean����ŵ������(HashMap)�С�
```
XML |--��ȡ--> Resource |--����--> BeanDefinition |--ע��--> BeanFactory
```
### ����ע�����


### Դ������
1. ����BeanFactory����
2. ���������ļ�ת����Resource��Resource����������bean������Ϣ����װ��BeanDefinition
3. ִ��BeanFactoryPostProcessor
4. ׼��������׼��BeanPostProcessor���㲥����������
5. ʵ����
6. ��ʼ��
   - ������� - populateBean
   - ʵ��Aware�ӿ� - ��ȡ������������(BeanFactroyAware BeanNameAware BeanClassLoaderAware) 
   - before - ApplicationContextAware
   - init-method
   - after - BeanPostProcessor( AOP ��ǿ )
7. ��ȡ����


### AOP
AOP(Aspect-Oriented Programming:����������) �ܹ�����Щ��ҵ���޹أ�ȴΪҵ��ģ������ͬ���õ��߼�������(������������־����Ȩ�޿��Ƶ�)��װ���������ڼ���ϵͳ���ظ����룬����ģ������϶ȣ���������δ���Ŀ���չ�ԺͿ�ά���ԡ�

Spring AOP�ǻ���**��̬����**��:
- ���Ҫ����Ķ���ʵ����ĳ���ӿڣ���ôSpring AOP��ʹ�� JDK��̬����ȥ�����������.
  ʹ�÷�������һ��ʵ�ִ���ӿڵ���, ͨ����д�����ķ�ʽ, ʵ�ֶԴ������ǿ. �ڵ��÷���ǰ���� InvocationHandler ������ 
- ������û��ʵ�ֽӿڵĶ��󣬾��޷�ʹ�� JDK Proxy ȥ���д����ˣ���ʱ��Spring AOP��ʹ�� Cglib ����һ��������������������Ϊ����.
  ʹ��ASM�������, �����ֽ���, ������������class�ļ����ؽ���, ͨ���޸��ֽ�����������, Ȼ����д����ķ���, ʵ�ֶԴ������ǿ.

### aop���ĸ���
- advice ֪ͨ������������Ĺ����Լ���ʱʹ��
- pointcut �е㣺�������ӵ�λ��
- join point ���ӵ㣺�������ɱ������λ��
- Aspect ���棺֪ͨ���е�Ľ��


### Spring�����ģʽ
- ����ģʽ:
  BeanĬ��������ǵ�����
- ����ģʽ:
  ����ģʽ��Ҫ��ͨ�� BeanFactory �� ApplicationContext ���� Bean ��������Ҳ��IOC����, ��Bean���й���.
- ����ģʽ:
  AOP �����ʵ�ַ�ʽ����ͨ������ʵ�֣�Spring ��Ҫʹ�� JDK ��̬����� CGLIB ����
- ģ�巽��:
  ��Ҫ��һЩ�������ݿ�����õ������� JdbcTemplate��JpaTemplate����Ϊ��ѯ���ݿ�Ľ������ӡ�ִ�в�ѯ���ر����Ӽ������̣��ǳ�������ģ�巽����


###��Spring AOP �� AspectJ AOP ����
Spring AOP ���ڶ�̬����ʵ�֣���������ʱ��ǿ��
AspectJ �����ڱ���ʱ��ǿ����Ҫ��3�ַ�ʽ��
1. ����ʱ֯�룺ָ������ǿ�Ĵ����Դ�������Ƕ��У�ֱ��ʹ�� AspectJ ��������������ˣ�����֮������һ���µ��࣬��Ҳ����Ϊһ�������� Java ��װ�ص�JVM��
2. �����֯�룺ָ���Ǵ����Ѿ�������� class �ļ������Ѿ���� jar ������ʱ��Ҫ��ǿ�Ļ������Ǳ����֯�룬�����������˵���������⣬���������ǿ�Ļ����Ϳ���ͨ�����ַ�ʽ��
3. �����ʱ֯�룺ָ������ JVM �������ʱ�����֯�롣


### FactoryBean �� BeanFactory ����
BeanFactory �� Bean �Ĺ����� ApplicationContext �ĸ��࣬IOC �����ĺ��ģ����������͹��� Bean ����
FactoryBean �� Bean������ͨ��ʵ�� FactoryBean �ӿ�(ʵ�ֽӿڵ���������Bean����, ������Bean�౾��)ȥ����ʵ���� Bean ���߼�. 


### Bean����������
1. ʵ����������һ��Bean����
2. ������ԣ�Ϊ���Ը�ֵpopulateBean
3. ��ʼ��
  ���ʵ����xxxAware�ӿڣ�ͨ����ͬ���͵�Aware�ӿ��õ�Spring��������Դ
  ���ʵ����BeanPostProcessor�ӿڣ����ص��ýӿڵ� postProcessBeforeInitialzation() �� postProcessAfterInitialization() ����
  ����������Զ���� init-method ���������ִ�� init-method ���õķ���
4. ����
  �����رպ����Beanʵ����DisposableBean�ӿڣ����ص��ýӿڵ�destroy()����
  ���������destroy-method���������ִ��destroy-method���õķ���


### ѭ������
����, ������ǰ������:
1. ��ȫ�ǹ��������µ�ѭ������
2. �����ǵ���

�����Ͻ����ʽ����������, ͨ������������ǰ�õ�δ��ʼ����ȫ�Ķ���  

- ��һ�����棺��������ʵ��������ʼ������ɵĶ���
- �ڶ������棺��������ʵ������ɣ�����δ��ʼ����ɵĶ���
- ���������棺����һ�����󹤳����ṩһ�������ڲ��࣬���ڴ������������еĶ���
https://zhuanlan.zhihu.com/p/368769721


### ΪʲôҪ�������棿
Spring����У��������Ĵ�������ʵ�����������ɵģ������뻺���ʱ����û�н���������Ժ�init�ģ���ʱ��Ӧ���ɴ���������԰�һ�㹤�������ȷ��뻺���С�
û�д���Ļ�������ν�ˣ���������Ҳ�С�


### Spring���񴫲�����(��Ϊ)
https://zhuanlan.zhihu.com/p/148504094
��������ķ�������֮������Ĵ���

PROPAGATION_REQUIRED�������ǰû�����񣬾ʹ���һ�������������ǰ�������񣬾ͼ����������Ҳ��ͨ�����ǵ�Ĭ��ѡ��
PROPAGATION_REQUIRES_NEW���������������۵�ǰ�治�������񣬶�����������
PROPAGATION_NESTED�������ǰ������������Ƕ��������ִ�С������ǰû��������REQUIRED����ִ�С�
PROPAGATION_NOT_SUPPORTED���Է�����ʽִ�в����������ǰ�������񣬾Ͱѵ�ǰ�������
PROPAGATION_NEVER���Է�����ʽִ�У������ǰ�����������׳��쳣��
PROPAGATION_MANDATORY��֧�ֵ�ǰ���������ǰ�������񣬾ͼ�������������ǰ���������񣬾��׳��쳣��
PROPAGATION_SUPPORTS��֧�ֵ�ǰ���������ǰ�������񣬾ͼ�������������ǰ���������񣬾��Է�����ִ�С�


### SpringBoot ��������
1. ׼�����������ݲ�ͬ�Ļ���������ͬ��Environment
2. ׼�������������ģ�Ϊ��ͬ�Ļ���ѡ��ͬ��Spring Context��Ȼ�������Դ������Bean
3. ��ʼ��������׶�ˢ��Spring Context������Ӧ��
4. ����������


### Spring Bean ������
singleton : Ψһ bean ʵ����Spring �е� bean Ĭ�϶��ǵ����ġ�
prototype : ÿ�����󶼻ᴴ��һ���µ� bean ʵ����
request : ÿһ��HTTP���󶼻����һ���µ�bean����bean���ڵ�ǰHTTP request ����Ч��
session : ÿһ��HTTP���󶼻����һ���µ� bean����bean���ڵ�ǰ HTTP session ����Ч��
global-session�� ȫ��session�����򣬽����ڻ���portlet��webӦ���в������壬Spring5�Ѿ�û���ˡ�Portlet���ܹ������������(���磺HTML)Ƭ�ε�С��Java Web��������ǻ���portlet������������servletһ������HTTP���󡣵��ǣ��� servlet ��ͬ��ÿ�� portlet ���в�ͬ�ĻỰ


### ����Bean���̰߳�ȫ����
ͨ��ʹ�õ�Bean������״̬��, �������̰߳�ȫ����
�������:
1. ����ThreadLocal��Ա����, ���ɱ��Ա�ŵ�����
2. �ı�bean��������Ϊprototype, ÿ�����󶼴����µ�Beanʵ��


### @Bean �� @Component������
1. @Bean ���ڷ���, @Component ������
2. @Bean ��ע�ķ���ͨ������Ϊ�������Bean, ��������ʹ�õ��������ʱ��; @Component �Զ���� �Զ�װ�䵽Spring������


### Spring������뼶��
��MySQL����, ֻ��һ��default����, �������ʹ�����ݿⱾ��ĸ��뼶��

 
### SpringBoot��SpringMVC
 SpringBoot = Spring MVC + ������ + Server(Tomcat Jetty)
 �����ֶ���������(spring.xml)


### spring��ô������ģ���ô������
- ���ʽ����
  ͨ�� TransactionTemplate����TransactionManager�ֶ���������
- ����ʽ����
  ���� @Transactional ��ȫע�ⷽʽʹ����� ʵ����ͨ�� AOP ʵ��
  Spring ����������ʱ�򴴽�һ�������࣬����ע�������ķ�����ʱ��ʵ�����ǵ��õ������� TransactionInterceptor ��invoke()������
  ��ͬһ���е�����û�� @Transactional ע��ķ����ڲ������� @Transactional ע��ķ�������@Transactional ע��ķ����������ʧЧ��


#### �������ӿ�
- PlatformTransactionManager: ������Եĺ���
- TransactionDefinition: ��������Ϣ
  - ���뼶��
    - PROPAGATION_REQUIRED
    - PROPAGATION_REQUIRES_NEW
    - PROPAGATION_NESTED
  - ������Ϊ
  - �ع����򣺷��ܼ��쳣(Runtime��Error)�Ż�ع�
  - �Ƿ�ֻ������Ϊÿһ����ѯ���洢���涼��Ϊһ���������������ͳ����Ĳ�ѯ����������DB���ж�����������п��ܲ�һ��
  - ����ʱ
- TransactionStatus: ��������״̬


### ע��ʵ��ԭ����������Լ�������ע����ôʵ��
- Ԫע��
  - @Retention������ע�ⱻ�����Ľ׶Σ�
  - @Target������ע��ʹ�õķ�Χ��
  - @Inherited������ע��ɼ̳У�
  - @Documented�������Ƿ�����javadoc�ĵ���
- Component
  ��һ������ʼ��ʱ������Component���͹�������
  �ڶ���������ָ��ɨ���ɨ��.class�ļ�������Resource����
  ������������.class�ļ���ע����࣬����MetadataReader����
  ���Ĳ���ʹ�õ�һ����ע����������˳���@Component�ࣻ
  ���岽������BeanDefinition��
  ����������BeanDefinitionע�ᵽSpring������
- AutoWired
  BeanPostProcessor

### Spring ��̬���� ��̬����
AspectJ AOP


### Spring Cloud����Щ���
�����֡���Netflix Eureka
�ͷ��˸��ؾ��⡪��Netflix Ribbon
��·������Netflix Hystrix
�������ء���Netflix Zuul
�ֲ�ʽ���á���Spring Cloud Config


### SpringMVC M V C
Model: ͨ��ָ��������
View: UI��ҳ��
Controller: ������������߼�


### �û�����MVC�ᷢ��ʲô
1. Http��������������ύ��DispatcherServlet��
2. Ѱ�Ҵ���������DispatcherServlet��������ѯһ������HandlerMapping���ҵ����������Controller��
3. ���ô�������DispatcherServlet�������ύ��Controller��
4. ����ҵ����ͷ��ؽ����Controller����ҵ���߼�����󣬷���ModelAndView��
5. ������ͼӳ�䲢����ģ�ͣ� DispatcherServlet��ѯһ������ViewResoler��ͼ���������ҵ�ModelAndViewָ������ͼ����model���ݸ�View��ʾ��
6. Http��Ӧ����ͼ���𽫽����ʾ���ͻ��ˡ�







