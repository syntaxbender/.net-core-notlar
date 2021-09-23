# .net-core-notlar
- project file
	- targetframework->netcoreapp5.0
	- itemgroup->nuget paketler burada

- program.cs
	- console uygulamalarından alışık olduğumuz main metodunun yer aldığı, uygulamamın ilk çalışmaya başladığı, startup dosyasının tanıtıldığı dosyadır.

- startup.cs
	configure ve configureservices adında 2 metod görürüz. bu metodlar otomatik olarak asp.net core tarafından çağrılır.
	- ConfigureServices
		- Configure metodundan önce çağrılır
		- bağımlılıklar, servisler burada dependency injection ile tanımlanır.
	- Configure
		- IApplicationBuilder app ve IWebHostEnvironment env adında 2 parametre alır.
		- environment interface ile development veya production ortamında olup olmama durumuna göre exception handler tanımlaması gibi çeşitli tanımlamalar yapılır.
		- app interface ile ise environment durumuna göre exception durumunda gerekli yönlendirmenin yapılması, routing mekanizmasının tanımlanması/yapılandırılması gibi çeşitli http request pipeline konfigürasyonu yapılır. Kısaca app ile bir http request karşısında nasıl bir response verilmeli bu konuların tanımlaması yapılır. Ayrıca middleware tanımlamaları da burada yapılır. Authentication, authorization, sessions, routing mekanizmaları da birer middlware olarak değerlendirilir.

		- Routing & Endpoints
			  - Öncelikle app.UseRouting(); kullanımı ile routing mekanizması middleware pipeline'a eklenir.
