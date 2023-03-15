# 1、纯mybatis 代码开发步骤

第一步：读取mybatis-config.xml配置文件<br>
第二步：构建一个SqlSessionFactory<br>
第三步：打开SqlSession<br>
第四步：获取Mapper接口对象<br>
第五步：调用Mapper对象的方法操作数据库<br>

            
            InputStream inputStream = Resources.getResourceAsStream("mybatis-config.xml");

            SqlSessionFactory factory = new SqlSessionFactoryBuilder().build(inputStream);

            SqlSession session = factory.openSession();

            ProductMapper productMapper = session.getMapper(ProductMapper.class);

            Product product = productMapper.find(1);


# 源码分析
## 第一步：
  读取mybatis-config.xml配置文件<br>
  InputStream inputStream = Resources.getResourceAsStream("mybatis-config.xml");
