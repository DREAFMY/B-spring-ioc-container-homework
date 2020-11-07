# B-spring-ioc-container-homework
Spring IoC Container Basics 课程课后作业。

主观题：
@Component 已经可以支持声明一个 bean 了，为何还要再弄个 @Bean 出来？

答：@Component注解添加在类上面，@Bean注解可以添加在方法上面。Spring可自动扫描到@Component注解的类和管理该类生成的bean的生命周期。但是这样会出现一个问题，当我们不需要使用某些类的时候，Spring还是会检测到被@Component注解的类和实例化产生bean，这样就造成了的资源浪费。而@Bean可以自定义需要实例化的bean，若需要使用某些不是Spring写的第三方库，为了能在我们的spring项目中使用这些库，就可以通过@Bean注解需要实例化的bean，这样就在不造成额外的资源浪。