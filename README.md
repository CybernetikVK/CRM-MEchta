<!DOCTYPE html>
<html lang="ru">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Mechta CRM - Алматы</title>
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
  <style>
    :root {
      --primary: #b91c1c;
      --primary-light: #fecaca;
      --dark: #1a1a1a;
      --light: #f8fafc;
    }

    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    .sidebar {
      background-color: var(--dark);
      transition: all 0.3s;
    }

    .bg-primary {
      background-color: var(--primary);
    }

    .text-primary {
      color: var(--primary);
    }

    .border-primary {
      border-color: var(--primary);
    }

    .hover\:bg-primary:hover {
      background-color: var(--primary);
    }

    .focus\:ring-primary:focus {
      --tw-ring-color: var(--primary);
    }

    .badge {
      display: inline-block;
      padding: 0.25em 0.4em;
      font-size: 75%;
      font-weight: 700;
      line-height: 1;
      text-align: center;
      white-space: nowrap;
      vertical-align: baseline;
      border-radius: 0.25rem;
    }

    .badge-primary {
      color: white;
      background-color: var(--primary);
    }

    .badge-secondary {
      color: var(--dark);
      background-color: var(--primary-light);
    }

    .tab-content {
      display: none;
    }

    .tab-content.active {
      display: block;
    }

    .property-card:hover {
      transform: translateY(-5px);
      box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
    }

    .property-card {
      transition: all 0.3s ease;
    }

    .dropdown-content {
      display: none;
      position: absolute;
      right: 0;
      background-color: white;
      min-width: 160px;
      box-shadow: 0px 8px 16px 0px rgba(0, 0, 0, 0.2);
      z-index: 1;
      border-radius: 0.375rem;
    }

    .dropdown:hover .dropdown-content {
      display: block;
    }

    @media (max-width: 768px) {
      .sidebar {
        position: absolute;
        z-index: 10;
        transform: translateX(-100%);
      }

      .sidebar.open {
        transform: translateX(0);
      }

      .mobile-menu-btn {
        display: block;
      }
    }
  </style>
</head>

<body class="bg-gray-100">
  <div class="flex h-screen overflow-hidden">
    <!-- Mobile menu button -->
    <button id="mobileMenuBtn" class="md:hidden fixed top-4 left-4 z-20 bg-white p-2 rounded shadow">
            <i class="fas fa-bars text-xl"></i>
        </button>

    <!-- Sidebar -->
    <div id="sidebar" class="sidebar text-white w-64 flex flex-col fixed md:relative h-full">
      <div class="p-4 flex items-center border-b border-gray-700">
        <i class="fas fa-building text-2xl mr-3 text-primary"></i>
        <span class="text-xl font-bold">RealEstate Алматы</span>
      </div>
      <div class="p-4 border-b border-gray-700">
        <div class="flex items-center">
          <img src="https://randomuser.me/api/portraits/men/1.jpg" alt="User" class="w-10 h-10 rounded-full">
          <div class="ml-3">
            <p class="text-sm font-medium">Администратор</p>
            <p class="text-xs text-gray-400">admin@realestate.kz</p>
          </div>
        </div>
      </div>
      <nav class="mt-2 flex-1 overflow-y-auto">
        <a href="#" class="block px-4 py-3 flex items-center text-white bg-primary">
          <i class="fas fa-tachometer-alt mr-3"></i> Главная
        </a>
        <a href="#properties"
          class="block px-4 py-3 flex items-center text-gray-300 hover:text-white hover:bg-gray-700">
          <i class="fas fa-home mr-3"></i> Объекты
        </a>
        <a href="#clients" class="block px-4 py-3 flex items-center text-gray-300 hover:text-white hover:bg-gray-700">
          <i class="fas fa-users mr-3"></i> Клиенты
        </a>
        <a href="#contracts" class="block px-4 py-3 flex items-center text-gray-300 hover:text-white hover:bg-gray-700">
          <i class="fas fa-file-contract mr-3"></i> Договоры
        </a>
        <a href="#showings" class="block px-4 py-3 flex items-center text-gray-300 hover:text-white hover:bg-gray-700">
          <i class="fas fa-calendar-alt mr-3"></i> Показы
        </a>
        <a href="#analytics" class="block px-4 py-3 flex items-center text-gray-300 hover:text-white hover:bg-gray-700">
          <i class="fas fa-chart-bar mr-3"></i> Аналитика
        </a>
        <a href="#settings" class="block px-4 py-3 flex items-center text-gray-300 hover:text-white hover:bg-gray-700">
          <i class="fas fa-cog mr-3"></i> Настройки
        </a>
      </nav>
      <div class="p-4 border-t border-gray-700">
        <a href="#" class="block px-4 py-2 text-gray-300 hover:text-white hover:bg-gray-700 rounded">
          <i class="fas fa-sign-out-alt mr-3"></i> Выйти
        </a>
      </div>
    </div>

    <!-- Main Content -->
    <div class="flex-1 flex flex-col overflow-hidden">
      <!-- Top Navigation -->
      <header class="bg-white shadow-sm">
        <div class="flex items-center justify-between px-6 py-3">
          <h1 class="text-xl font-semibold text-gray-800" id="pageTitle">Главная панель</h1>
          <div class="flex items-center space-x-4">
            <div class="relative hidden md:block">
              <input type="text" placeholder="Поиск..." class="pl-10 pr-4 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-primary w-64">
              <i class="fas fa-search absolute left-3 top-3 text-gray-400"></i>
            </div>
            <div class="flex items-center space-x-4">
              <div class="relative">
                <i class="fas fa-bell text-gray-600 text-xl cursor-pointer"></i>
                <span class="absolute top-0 right-0 h-2 w-2 rounded-full bg-primary"></span>
              </div>
              <div class="dropdown relative">
                <button class="flex items-center space-x-2 focus:outline-none">
                                    <img src="https://randomuser.me/api/portraits/men/1.jpg" alt="User" class="w-8 h-8 rounded-full">
                                    <span class="text-sm font-medium hidden md:inline">Администратор</span>
                                    <i class="fas fa-chevron-down text-xs"></i>
                                </button>
                <div class="dropdown-content mt-2 py-1">
                  <a href="#" class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">Профиль</a>
                  <a href="#" class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">Настройки</a>
                  <div class="border-t border-gray-200"></div>
                  <a href="#" class="block px-4 py-2 text-sm text-gray-700 hover:bg-gray-100">Выйти</a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </header>

      <!-- Main Content Area -->
      <main class="flex-1 overflow-y-auto p-6 bg-gray-100">
        <!-- Dashboard Content -->
        <div id="dashboard" class="tab-content active">
          <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-6 mb-6">
            <!-- Stats Cards -->
            <div class="bg-white rounded-lg shadow p-6">
              <div class="flex items-center justify-between">
                <div>
                  <p class="text-gray-500">Всего объектов</p>
                  <h3 class="text-2xl font-bold">124</h3>
                  <p class="text-sm text-gray-500 mt-1"><span class="text-green-500">+5</span> за неделю</p>
                </div>
                <div class="p-3 rounded-full bg-red-100 text-primary">
                  <i class="fas fa-home text-xl"></i>
                </div>
              </div>
            </div>

            <div class="bg-white rounded-lg shadow p-6">
              <div class="flex items-center justify-between">
                <div>
                  <p class="text-gray-500">Активные клиенты</p>
                  <h3 class="text-2xl font-bold">56</h3>
                  <p class="text-sm text-gray-500 mt-1"><span class="text-green-500">+3</span> за неделю</p>
                </div>
                <div class="p-3 rounded-full bg-red-100 text-primary">
                  <i class="fas fa-users text-xl"></i>
                </div>
              </div>
            </div>

            <div class="bg-white rounded-lg shadow p-6">
              <div class="flex items-center justify-between">
                <div>
                  <p class="text-gray-500">Запланированные показы</p>
                  <h3 class="text-2xl font-bold">12</h3>
                  <p class="text-sm text-gray-500 mt-1"><span class="text-red-500">-2</span> за неделю</p>
                </div>
                <div class="p-3 rounded-full bg-red-100 text-primary">
                  <i class="fas fa-calendar-alt text-xl"></i>
                </div>
              </div>
            </div>

            <div class="bg-white rounded-lg shadow p-6">
              <div class="flex items-center justify-between">
                <div>
                  <p class="text-gray-500">Заключенные сделки</p>
                  <h3 class="text-2xl font-bold">8</h3>
                  <p class="text-sm text-gray-500 mt-1"><span class="text-green-500">+2</span> за неделю</p>
                </div>
                <div class="p-3 rounded-full bg-red-100 text-primary">
                  <i class="fas fa-file-signature text-xl"></i>
                </div>
              </div>
            </div>
          </div>

          <div class="grid grid-cols-1 lg:grid-cols-3 gap-6 mb-6">
            <!-- Recent Activities -->
            <div class="lg:col-span-2 bg-white rounded-lg shadow overflow-hidden">
              <div class="px-6 py-4 border-b border-gray-200 flex justify-between items-center">
                <h3 class="text-lg font-medium text-gray-900">Последние действия</h3>
                <a href="#" class="text-sm text-primary hover:underline">Показать все</a>
              </div>
              <div class="divide-y divide-gray-200">
                <div class="px-6 py-4">
                  <div class="flex items-center">
                    <div class="flex-shrink-0 bg-red-100 p-2 rounded-full text-primary">
                      <i class="fas fa-home"></i>
                    </div>
                    <div class="ml-4">
                      <p class="text-sm font-medium text-gray-900">Добавлен новый объект</p>
                      <p class="text-sm text-gray-500">Квартира в районе Алмалы, 3 комнаты, 12 000 000 ₸</p>
                    </div>
                    <div class="ml-auto text-sm text-gray-500">2 часа назад</div>
                  </div>
                </div>
                <div class="px-6 py-4">
                  <div class="flex items-center">
                    <div class="flex-shrink-0 bg-red-100 p-2 rounded-full text-primary">
                      <i class="fas fa-users"></i>
                    </div>
                    <div class="ml-4">
                      <p class="text-sm font-medium text-gray-900">Новый клиент</p>
                      <p class="text-sm text-gray-500">Иванов Иван, ищет 2-комнатную квартиру в Бостандыкском районе</p>
                    </div>
                    <div class="ml-auto text-sm text-gray-500">5 часов назад</div>
                  </div>
                </div>
                <div class="px-6 py-4">
                  <div class="flex items-center">
                    <div class="flex-shrink-0 bg-red-100 p-2 rounded-full text-primary">
                      <i class="fas fa-calendar-alt"></i>
                    </div>
                    <div class="ml-4">
                      <p class="text-sm font-medium text-gray-900">Запланирован показ</p>
                      <p class="text-sm text-gray-500">Петров Петр, квартира на ул. Абая, 15.05.2023 в 18:00</p>
                    </div>
                    <div class="ml-auto text-sm text-gray-500">Вчера</div>
                  </div>
                </div>
                <div class="px-6 py-4">
                  <div class="flex items-center">
                    <div class="flex-shrink-0 bg-red-100 p-2 rounded-full text-primary">
                      <i class="fas fa-file-signature"></i>
                    </div>
                    <div class="ml-4">
                      <p class="text-sm font-medium text-gray-900">Заключен договор</p>
                      <p class="text-sm text-gray-500">Аренда квартиры на ул. Толе би, 120 000 ₸/мес</p>
                    </div>
                    <div class="ml-auto text-sm text-gray-500">2 дня назад</div>
                  </div>
                </div>
              </div>
            </div>

            <!-- Upcoming Appointments -->
            <div class="bg-white rounded-lg shadow overflow-hidden">
              <div class="px-6 py-4 border-b border-gray-200 flex justify-between items-center">
                <h3 class="text-lg font-medium text-gray-900">Ближайшие показы</h3>
                <a href="#" class="text-sm text-primary hover:underline">Показать все</a>
              </div>
              <div class="divide-y divide-gray-200">
                <div class="px-6 py-4">
                  <div class="flex items-center">
                    <div class="flex-shrink-0">
                      <img class="h-10 w-10 rounded-full" src="https://randomuser.me/api/portraits/women/1.jpg" alt="">
                    </div>
                    <div class="ml-4">
                      <p class="text-sm font-medium text-gray-900">Смирнова Анна</p>
                      <p class="text-sm text-gray-500">Квартира на ул. Фурманова</p>
                      <p class="text-xs text-gray-400 mt-1"><i class="far fa-clock mr-1"></i> 15.05.2023 в 18:00</p>
                    </div>
                    <div class="ml-auto">
                      <span class="badge badge-primary">Подтвержден</span>
                    </div>
                  </div>
                </div>
                <div class="px-6 py-4">
                  <div class="flex items-center">
                    <div class="flex-shrink-0">
                      <img class="h-10 w-10 rounded-full" src="https://randomuser.me/api/portraits/men/2.jpg" alt="">
                    </div>
                    <div class="ml-4">
                      <p class="text-sm font-medium text-gray-900">Кузнецов Дмитрий</p>
                      <p class="text-sm text-gray-500">Дом в районе Коктем</p>
                      <p class="text-xs text-gray-400 mt-1"><i class="far fa-clock mr-1"></i> 16.05.2023 в 11:00</p>
                    </div>
                    <div class="ml-auto">
                      <span class="badge badge-secondary">Ожидание</span>
                    </div>
                  </div>
                </div>
                <div class="px-6 py-4">
                  <div class="flex items-center">
                    <div class="flex-shrink-0">
                      <img class="h-10 w-10 rounded-full" src="https://randomuser.me/api/portraits/women/3.jpg" alt="">
                    </div>
                    <div class="ml-4">
                      <p class="text-sm font-medium text-gray-900">Петрова Ольга</p>
                      <p class="text-sm text-gray-500">Квартира на ул. Назарбаева</p>
                      <p class="text-xs text-gray-400 mt-1"><i class="far fa-clock mr-1"></i> 17.05.2023 в 16:30</p>
                    </div>
                    <div class="ml-auto">
                      <span class="badge badge-primary">Подтвержден</span>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <!-- Recent Properties -->
          <div class="bg-white rounded-lg shadow overflow-hidden mb-6">
            <div class="px-6 py-4 border-b border-gray-200 flex justify-between items-center">
              <h3 class="text-lg font-medium text-gray-900">Последние добавленные объекты</h3>
              <a href="#" class="text-sm text-primary hover:underline">Показать все</a>
            </div>
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 p-6">
              <div class="property-card bg-white rounded-lg shadow-md overflow-hidden border border-gray-200">
                <div class="relative">
                  <img src="https://images.unsplash.com/photo-1560448204-e02f11c3d0e2?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Property" class="w-full h-48 object-cover">
                  <div class="absolute top-2 right-2 bg-primary text-white text-xs px-2 py-1 rounded">Новый</div>
                </div>
                <div class="p-4">
                  <div class="flex justify-between items-start">
                    <h4 class="font-bold text-lg">Квартира в Алмалы</h4>
                    <span class="text-primary font-bold">12 000 000 ₸</span>
                  </div>
                  <p class="text-gray-600 text-sm mt-1"><i class="fas fa-map-marker-alt mr-1 text-primary"></i> ул.
                    Абая, 123</p>
                  <div class="flex mt-3 text-sm text-gray-500">
                    <span class="mr-3"><i class="fas fa-bed mr-1"></i> 3</span>
                    <span class="mr-3"><i class="fas fa-bath mr-1"></i> 2</span>
                    <span><i class="fas fa-vector-square mr-1"></i> 85 м²</span>
                  </div>
                  <div class="mt-3 flex justify-between items-center">
                    <span class="text-xs bg-green-100 text-green-800 px-2 py-1 rounded">Свободен</span>
                    <button class="text-primary text-sm font-medium hover:underline">Подробнее</button>
                  </div>
                </div>
              </div>

              <div class="property-card bg-white rounded-lg shadow-md overflow-hidden border border-gray-200">
                <div class="relative">
                  <img src="https://images.unsplash.com/photo-1512917774080-9991f1c4c750?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Property" class="w-full h-48 object-cover">
                </div>
                <div class="p-4">
                  <div class="flex justify-between items-start">
                    <h4 class="font-bold text-lg">Дом в Бостандыке</h4>
                    <span class="text-primary font-bold">45 000 000 ₸</span>
                  </div>
                  <p class="text-gray-600 text-sm mt-1"><i class="fas fa-map-marker-alt mr-1 text-primary"></i> ул. Толе
                    би, 45</p>
                  <div class="flex mt-3 text-sm text-gray-500">
                    <span class="mr-3"><i class="fas fa-bed mr-1"></i> 4</span>
                    <span class="mr-3"><i class="fas fa-bath mr-1"></i> 3</span>
                    <span><i class="fas fa-vector-square mr-1"></i> 150 м²</span>
                  </div>
                  <div class="mt-3 flex justify-between items-center">
                    <span class="text-xs bg-yellow-100 text-yellow-800 px-2 py-1 rounded">В процессе</span>
                    <button class="text-primary text-sm font-medium hover:underline">Подробнее</button>
                  </div>
                </div>
              </div>

              <div class="property-card bg-white rounded-lg shadow-md overflow-hidden border border-gray-200">
                <div class="relative">
                  <img src="https://images.unsplash.com/photo-1484154218962-a197022b5858?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="Property" class="w-full h-48 object-cover">
                </div>
                <div class="p-4">
                  <div class="flex justify-between items-start">
                    <h4 class="font-bold text-lg">Квартира в Медеуском</h4>
                    <span class="text-primary font-bold">9 500 000 ₸</span>
                  </div>
                  <p class="text-gray-600 text-sm mt-1"><i class="fas fa-map-marker-alt mr-1 text-primary"></i> ул.
                    Гоголя, 78</p>
                  <div class="flex mt-3 text-sm text-gray-500">
                    <span class="mr-3"><i class="fas fa-bed mr-1"></i> 2</span>
                    <span class="mr-3"><i class="fas fa-bath mr-1"></i> 1</span>
                    <span><i class="fas fa-vector-square mr-1"></i> 65 м²</span>
                  </div>
                  <div class="mt-3 flex justify-between items-center">
                    <span class="text-xs bg-red-100 text-red-800 px-2 py-1 rounded">Сдан</span>
                    <button class="text-primary text-sm font-medium hover:underline">Подробнее</button>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Properties Content -->
        <div id="properties" class="tab-content">
          <div class="flex justify-between items-center mb-6">
            <h2 class="text-2xl font-bold text-gray-800">Управление объектами</h2>
            <button class="bg-primary hover:bg-red-800 text-white px-4 py-2 rounded-lg flex items-center">
                            <i class="fas fa-plus mr-2"></i> Добавить объект
                        </button>
          </div>

          <div class="bg-white rounded-lg shadow overflow-hidden mb-6">
            <div class="px-6 py-4 border-b border-gray-200">
              <div class="flex flex-col md:flex-row md:items-center md:justify-between">
                <div class="mb-4 md:mb-0">
                  <div class="relative">
                    <input type="text" placeholder="Поиск объектов..." class="pl-10 pr-4 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-primary w-full md:w-64">
                    <i class="fas fa-search absolute left-3 top-3 text-gray-400"></i>
                  </div>
                </div>
                <div class="flex space-x-2">
                  <select class="border rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-primary">
                                        <option>Все районы</option>
                                        <option>Алмалы</option>
                                        <option>Бостандыкский</option>
                                        <option>Медеуский</option>
                                        <option>Ауэзовский</option>
                                    </select>
                  <select class="border rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-primary">
                                        <option>Все типы</option>
                                        <option>Квартира</option>
                                        <option>Дом</option>
                                        <option>Комната</option>
                                        <option>Офис</option>
                                    </select>
                  <select class="border rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-primary">
                                        <option>Все статусы</option>
                                        <option>Свободен</option>
                                        <option>Сдан</option>
                                        <option>В процессе</option>
                                    </select>
                </div>
              </div>
            </div>
            <div class="overflow-x-auto">
              <table class="min-w-full divide-y divide-gray-200">
                <thead class="bg-gray-50">
                  <tr>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Адрес</th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Тип</th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Комнат</th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Площадь
                    </th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Цена</th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Статус</th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Действия
                    </th>
                  </tr>
                </thead>
                <tbody class="bg-white divide-y divide-gray-200">
                  <tr>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="flex items-center">
                        <div class="flex-shrink-0 h-10 w-10">
                          <img class="h-10 w-10 rounded-full" src="https://images.unsplash.com/photo-1560448204-e02f11c3d0e2?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="">
                        </div>
                        <div class="ml-4">
                          <div class="text-sm font-medium text-gray-900">ул. Абая, 123</div>
                          <div class="text-sm text-gray-500">Алмалы</div>
                        </div>
                      </div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">Квартира</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">3</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">85 м²</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">12 000 000 ₸</td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-green-100 text-green-800">Свободен</span>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-edit"></i></a>
                      <a href="#" class="text-red-600 hover:text-red-900"><i class="fas fa-trash"></i></a>
                    </td>
                  </tr>
                  <tr>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="flex items-center">
                        <div class="flex-shrink-0 h-10 w-10">
                          <img class="h-10 w-10 rounded-full" src="https://images.unsplash.com/photo-1512917774080-9991f1c4c750?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="">
                        </div>
                        <div class="ml-4">
                          <div class="text-sm font-medium text-gray-900">ул. Толе би, 45</div>
                          <div class="text-sm text-gray-500">Бостандыкский</div>
                        </div>
                      </div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">Дом</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">4</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">150 м²</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">45 000 000 ₸</td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-yellow-100 text-yellow-800">В процессе</span>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-edit"></i></a>
                      <a href="#" class="text-red-600 hover:text-red-900"><i class="fas fa-trash"></i></a>
                    </td>
                  </tr>
                  <tr>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="flex items-center">
                        <div class="flex-shrink-0 h-10 w-10">
                          <img class="h-10 w-10 rounded-full" src="https://images.unsplash.com/photo-1484154218962-a197022b5858?ixlib=rb-1.2.1&auto=format&fit=crop&w=500&q=60" alt="">
                        </div>
                        <div class="ml-4">
                          <div class="text-sm font-medium text-gray-900">ул. Гоголя, 78</div>
                          <div class="text-sm text-gray-500">Медеуский</div>
                        </div>
                      </div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">Квартира</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">2</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">65 м²</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">9 500 000 ₸</td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-red-100 text-red-800">Сдан</span>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-edit"></i></a>
                      <a href="#" class="text-red-600 hover:text-red-900"><i class="fas fa-trash"></i></a>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
            <div class="px-6 py-4 border-t border-gray-200 flex items-center justify-between">
              <div class="text-sm text-gray-500">
                Показано <span class="font-medium">1</span> до <span class="font-medium">3</span> из
                <span class="font-medium">124</span> объектов
              </div>
              <div class="flex space-x-2">
                <button class="px-3 py-1 border rounded text-gray-500 hover:bg-gray-50">Назад</button>
                <button class="px-3 py-1 border rounded bg-primary text-white hover:bg-red-800">1</button>
                <button class="px-3 py-1 border rounded text-gray-500 hover:bg-gray-50">2</button>
                <button class="px-3 py-1 border rounded text-gray-500 hover:bg-gray-50">3</button>
                <button class="px-3 py-1 border rounded text-gray-500 hover:bg-gray-50">Вперед</button>
              </div>
            </div>
          </div>
        </div>

        <!-- Clients Content -->
        <div id="clients" class="tab-content">
          <div class="flex justify-between items-center mb-6">
            <h2 class="text-2xl font-bold text-gray-800">Управление клиентами</h2>
            <button class="bg-primary hover:bg-red-800 text-white px-4 py-2 rounded-lg flex items-center">
                            <i class="fas fa-plus mr-2"></i> Добавить клиента
                        </button>
          </div>

          <div class="bg-white rounded-lg shadow overflow-hidden mb-6">
            <div class="px-6 py-4 border-b border-gray-200">
              <div class="flex flex-col md:flex-row md:items-center md:justify-between">
                <div class="mb-4 md:mb-0">
                  <div class="relative">
                    <input type="text" placeholder="Поиск клиентов..." class="pl-10 pr-4 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-primary w-full md:w-64">
                    <i class="fas fa-search absolute left-3 top-3 text-gray-400"></i>
                  </div>
                </div>
                <div class="flex space-x-2">
                  <select class="border rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-primary">
                                        <option>Все статусы</option>
                                        <option>Холодный</option>
                                        <option>Тёплый</option>
                                        <option>Горячий</option>
                                    </select>
                  <select class="border rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-primary">
                                        <option>Все типы</option>
                                        <option>Аренда</option>
                                        <option>Покупка</option>
                                    </select>
                  <select class="border rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-primary">
                                        <option>Все риэлторы</option>
                                        <option>Иванов И.</option>
                                        <option>Петров П.</option>
                                        <option>Сидорова С.</option>
                                    </select>
                </div>
              </div>
            </div>
            <div class="overflow-x-auto">
              <table class="min-w-full divide-y divide-gray-200">
                <thead class="bg-gray-50">
                  <tr>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Клиент</th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Контакты
                    </th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Тип</th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Статус</th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Риэлтор
                    </th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Действия
                    </th>
                  </tr>
                </thead>
                <tbody class="bg-white divide-y divide-gray-200">
                  <tr>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="flex items-center">
                        <div class="flex-shrink-0 h-10 w-10">
                          <img class="h-10 w-10 rounded-full" src="https://randomuser.me/api/portraits/men/32.jpg" alt="">
                        </div>
                        <div class="ml-4">
                          <div class="text-sm font-medium text-gray-900">Иванов Иван</div>
                          <div class="text-sm text-gray-500">Добавлен: 12.05.2023</div>
                        </div>
                      </div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="text-sm text-gray-900">+7 777 123 4567</div>
                      <div class="text-sm text-gray-500">ivanov@example.com</div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">Покупка</td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-blue-100 text-blue-800">Тёплый</span>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">Иванов И.</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-edit"></i></a>
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-eye"></i></a>
                      <a href="#" class="text-red-600 hover:text-red-900"><i class="fas fa-trash"></i></a>
                    </td>
                  </tr>
                  <tr>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="flex items-center">
                        <div class="flex-shrink-0 h-10 w-10">
                          <img class="h-10 w-10 rounded-full" src="https://randomuser.me/api/portraits/women/44.jpg" alt="">
                        </div>
                        <div class="ml-4">
                          <div class="text-sm font-medium text-gray-900">Петрова Ольга</div>
                          <div class="text-sm text-gray-500">Добавлен: 10.05.2023</div>
                        </div>
                      </div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="text-sm text-gray-900">+7 777 765 4321</div>
                      <div class="text-sm text-gray-500">petrova@example.com</div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">Аренда</td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-red-100 text-red-800">Горячий</span>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">Сидорова С.</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-edit"></i></a>
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-eye"></i></a>
                      <a href="#" class="text-red-600 hover:text-red-900"><i class="fas fa-trash"></i></a>
                    </td>
                  </tr>
                  <tr>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="flex items-center">
                        <div class="flex-shrink-0 h-10 w-10">
                          <img class="h-10 w-10 rounded-full" src="https://randomuser.me/api/portraits/men/67.jpg" alt="">
                        </div>
                        <div class="ml-4">
                          <div class="text-sm font-medium text-gray-900">Сидоров Алексей</div>
                          <div class="text-sm text-gray-500">Добавлен: 05.05.2023</div>
                        </div>
                      </div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="text-sm text-gray-900">+7 777 555 6677</div>
                      <div class="text-sm text-gray-500">sidorov@example.com</div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">Покупка</td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-gray-100 text-gray-800">Холодный</span>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">Петров П.</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-edit"></i></a>
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-eye"></i></a>
                      <a href="#" class="text-red-600 hover:text-red-900"><i class="fas fa-trash"></i></a>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
            <div class="px-6 py-4 border-t border-gray-200 flex items-center justify-between">
              <div class="text-sm text-gray-500">
                Показано <span class="font-medium">1</span> до <span class="font-medium">3</span> из
                <span class="font-medium">56</span> клиентов
              </div>
              <div class="flex space-x-2">
                <button class="px-3 py-1 border rounded text-gray-500 hover:bg-gray-50">Назад</button>
                <button class="px-3 py-1 border rounded bg-primary text-white hover:bg-red-800">1</button>
                <button class="px-3 py-1 border rounded text-gray-500 hover:bg-gray-50">2</button>
                <button class="px-3 py-1 border rounded text-gray-500 hover:bg-gray-50">3</button>
                <button class="px-3 py-1 border rounded text-gray-500 hover:bg-gray-50">Вперед</button>
              </div>
            </div>
          </div>
        </div>

        <!-- Contracts Content -->
        <div id="contracts" class="tab-content">
          <div class="flex justify-between items-center mb-6">
            <h2 class="text-2xl font-bold text-gray-800">Управление договорами</h2>
            <button class="bg-primary hover:bg-red-800 text-white px-4 py-2 rounded-lg flex items-center">
                            <i class="fas fa-plus mr-2"></i> Добавить договор
                        </button>
          </div>

          <div class="bg-white rounded-lg shadow overflow-hidden mb-6">
            <div class="px-6 py-4 border-b border-gray-200">
              <div class="flex flex-col md:flex-row md:items-center md:justify-between">
                <div class="mb-4 md:mb-0">
                  <div class="relative">
                    <input type="text" placeholder="Поиск договоров..." class="pl-10 pr-4 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-primary w-full md:w-64">
                    <i class="fas fa-search absolute left-3 top-3 text-gray-400"></i>
                  </div>
                </div>
                <div class="flex space-x-2">
                  <select class="border rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-primary">
                                        <option>Все типы</option>
                                        <option>Аренда</option>
                                        <option>Покупка</option>
                                        <option>Услуги</option>
                                    </select>
                  <select class="border rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-primary">
                                        <option>Все статусы</option>
                                        <option>Активный</option>
                                        <option>Завершен</option>
                                        <option>Отменен</option>
                                    </select>
                  <input type="month" class="border rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-primary">
                </div>
              </div>
            </div>
            <div class="overflow-x-auto">
              <table class="min-w-full divide-y divide-gray-200">
                <thead class="bg-gray-50">
                  <tr>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Номер</th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Тип</th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Клиент</th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Объект</th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Дата</th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Сумма</th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Статус</th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Действия
                    </th>
                  </tr>
                </thead>
                <tbody class="bg-white divide-y divide-gray-200">
                  <tr>
                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900">#RE-2023-045</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">Аренда</td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="flex items-center">
                        <div class="flex-shrink-0 h-10 w-10">
                          <img class="h-10 w-10 rounded-full" src="https://randomuser.me/api/portraits/women/44.jpg" alt="">
                        </div>
                        <div class="ml-4">
                          <div class="text-sm font-medium text-gray-900">Петрова Ольга</div>
                        </div>
                      </div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">ул. Толе би, 45</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">15.05.2023</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">120 000 ₸/мес</td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-green-100 text-green-800">Активный</span>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-file-pdf"></i></a>
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-eye"></i></a>
                      <a href="#" class="text-red-600 hover:text-red-900"><i class="fas fa-trash"></i></a>
                    </td>
                  </tr>
                  <tr>
                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900">#RE-2023-044</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">Покупка</td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="flex items-center">
                        <div class="flex-shrink-0 h-10 w-10">
                          <img class="h-10 w-10 rounded-full" src="https://randomuser.me/api/portraits/men/32.jpg" alt="">
                        </div>
                        <div class="ml-4">
                          <div class="text-sm font-medium text-gray-900">Иванов Иван</div>
                        </div>
                      </div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">ул. Абая, 123</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">10.05.2023</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">12 000 000 ₸</td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-yellow-100 text-yellow-800">В процессе</span>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-file-pdf"></i></a>
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-eye"></i></a>
                      <a href="#" class="text-red-600 hover:text-red-900"><i class="fas fa-trash"></i></a>
                    </td>
                  </tr>
                  <tr>
                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium text-gray-900">#RE-2023-043</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">Услуги</td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="flex items-center">
                        <div class="flex-shrink-0 h-10 w-10">
                          <img class="h-10 w-10 rounded-full" src="https://randomuser.me/api/portraits/men/67.jpg" alt="">
                        </div>
                        <div class="ml-4">
                          <div class="text-sm font-medium text-gray-900">Сидоров Алексей</div>
                        </div>
                      </div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">-</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">05.05.2023</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">50 000 ₸</td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-gray-100 text-gray-800">Завершен</span>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-file-pdf"></i></a>
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-eye"></i></a>
                      <a href="#" class="text-red-600 hover:text-red-900"><i class="fas fa-trash"></i></a>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
            <div class="px-6 py-4 border-t border-gray-200 flex items-center justify-between">
              <div class="text-sm text-gray-500">
                Показано <span class="font-medium">1</span> до <span class="font-medium">3</span> из
                <span class="font-medium">8</span> договоров
              </div>
              <div class="flex space-x-2">
                <button class="px-3 py-1 border rounded text-gray-500 hover:bg-gray-50">Назад</button>
                <button class="px-3 py-1 border rounded bg-primary text-white hover:bg-red-800">1</button>
                <button class="px-3 py-1 border rounded text-gray-500 hover:bg-gray-50">2</button>
                <button class="px-3 py-1 border rounded text-gray-500 hover:bg-gray-50">3</button>
                <button class="px-3 py-1 border rounded text-gray-500 hover:bg-gray-50">Вперед</button>
              </div>
            </div>
          </div>
        </div>

        <!-- Showings Content -->
        <div id="showings" class="tab-content">
          <div class="flex justify-between items-center mb-6">
            <h2 class="text-2xl font-bold text-gray-800">Управление показами</h2>
            <button class="bg-primary hover:bg-red-800 text-white px-4 py-2 rounded-lg flex items-center">
                            <i class="fas fa-plus mr-2"></i> Запланировать показ
                        </button>
          </div>

          <div class="grid grid-cols-1 lg:grid-cols-3 gap-6 mb-6">
            <div class="lg:col-span-2 bg-white rounded-lg shadow overflow-hidden">
              <div class="px-6 py-4 border-b border-gray-200 flex justify-between items-center">
                <h3 class="text-lg font-medium text-gray-900">Календарь показов</h3>
                <div class="flex space-x-2">
                  <button class="px-3 py-1 border rounded text-gray-500 hover:bg-gray-50">День</button>
                  <button class="px-3 py-1 border rounded text-gray-500 hover:bg-gray-50">Неделя</button>
                  <button class="px-3 py-1 border rounded bg-primary text-white hover:bg-red-800">Месяц</button>
                </div>
              </div>
              <div class="p-6">
                <!-- Calendar Placeholder -->
                <div class="bg-gray-100 rounded-lg p-4 h-96 flex items-center justify-center">
                  <p class="text-gray-500">Календарь показов будет здесь</p>
                </div>
              </div>
            </div>

            <div class="bg-white rounded-lg shadow overflow-hidden">
              <div class="px-6 py-4 border-b border-gray-200">
                <h3 class="text-lg font-medium text-gray-900">Ближайшие показы</h3>
              </div>
              <div class="divide-y divide-gray-200">
                <div class="px-6 py-4">
                  <div class="flex items-center">
                    <div class="flex-shrink-0 bg-red-100 p-2 rounded-full text-primary">
                      <i class="fas fa-calendar-alt"></i>
                    </div>
                    <div class="ml-4">
                      <p class="text-sm font-medium text-gray-900">Сегодня, 18:00</p>
                      <p class="text-sm text-gray-500">Петрова Ольга - Квартира на ул. Фурманова</p>
                    </div>
                  </div>
                </div>
                <div class="px-6 py-4">
                  <div class="flex items-center">
                    <div class="flex-shrink-0 bg-red-100 p-2 rounded-full text-primary">
                      <i class="fas fa-calendar-alt"></i>
                    </div>
                    <div class="ml-4">
                      <p class="text-sm font-medium text-gray-900">Завтра, 11:00</p>
                      <p class="text-sm text-gray-500">Кузнецов Дмитрий - Дом в районе Коктем</p>
                    </div>
                  </div>
                </div>
                <div class="px-6 py-4">
                  <div class="flex items-center">
                    <div class="flex-shrink-0 bg-red-100 p-2 rounded-full text-primary">
                      <i class="fas fa-calendar-alt"></i>
                    </div>
                    <div class="ml-4">
                      <p class="text-sm font-medium text-gray-900">17.05.2023, 16:30</p>
                      <p class="text-sm text-gray-500">Петрова Ольга - Квартира на ул. Назарбаева</p>
                    </div>
                  </div>
                </div>
                <div class="px-6 py-4">
                  <div class="flex items-center">
                    <div class="flex-shrink-0 bg-red-100 p-2 rounded-full text-primary">
                      <i class="fas fa-calendar-alt"></i>
                    </div>
                    <div class="ml-4">
                      <p class="text-sm font-medium text-gray-900">20.05.2023, 14:00</p>
                      <p class="text-sm text-gray-500">Иванов Иван - Квартира на ул. Абая</p>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>

          <div class="bg-white rounded-lg shadow overflow-hidden mb-6">
            <div class="px-6 py-4 border-b border-gray-200 flex justify-between items-center">
              <h3 class="text-lg font-medium text-gray-900">Все показы</h3>
              <div class="flex space-x-2">
                <select class="border rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-primary">
                                    <option>Все статусы</option>
                                    <option>Запланирован</option>
                                    <option>Проведен</option>
                                    <option>Отменен</option>
                                </select>
                <input type="month" class="border rounded-lg px-3 py-2 focus:outline-none focus:ring-2 focus:ring-primary">
              </div>
            </div>
            <div class="overflow-x-auto">
              <table class="min-w-full divide-y divide-gray-200">
                <thead class="bg-gray-50">
                  <tr>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Дата и
                      время</th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Клиент</th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Объект</th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Риэлтор
                    </th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Статус</th>
                    <th scope="col"
                      class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">Действия
                    </th>
                  </tr>
                </thead>
                <tbody class="bg-white divide-y divide-gray-200">
                  <tr>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="text-sm font-medium text-gray-900">15.05.2023, 18:00</div>
                      <div class="text-sm text-gray-500">ул. Фурманова, 56</div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="flex items-center">
                        <div class="flex-shrink-0 h-10 w-10">
                          <img class="h-10 w-10 rounded-full" src="https://randomuser.me/api/portraits/women/1.jpg" alt="">
                        </div>
                        <div class="ml-4">
                          <div class="text-sm font-medium text-gray-900">Смирнова Анна</div>
                        </div>
                      </div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">Квартира, 3 комн., 85 м²</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">Иванов И.</td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-green-100 text-green-800">Запланирован</span>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-edit"></i></a>
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-eye"></i></a>
                      <a href="#" class="text-red-600 hover:text-red-900"><i class="fas fa-trash"></i></a>
                    </td>
                  </tr>
                  <tr>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="text-sm font-medium text-gray-900">16.05.2023, 11:00</div>
                      <div class="text-sm text-gray-500">ул. Коктем, 12</div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="flex items-center">
                        <div class="flex-shrink-0 h-10 w-10">
                          <img class="h-10 w-10 rounded-full" src="https://randomuser.me/api/portraits/men/2.jpg" alt="">
                        </div>
                        <div class="ml-4">
                          <div class="text-sm font-medium text-gray-900">Кузнецов Дмитрий</div>
                        </div>
                      </div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">Дом, 4 комн., 150 м²</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">Петров П.</td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-yellow-100 text-yellow-800">Подтверждение</span>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-edit"></i></a>
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-eye"></i></a>
                      <a href="#" class="text-red-600 hover:text-red-900"><i class="fas fa-trash"></i></a>
                    </td>
                  </tr>
                  <tr>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="text-sm font-medium text-gray-900">10.05.2023, 15:30</div>
                      <div class="text-sm text-gray-500">ул. Абая, 123</div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <div class="flex items-center">
                        <div class="flex-shrink-0 h-10 w-10">
                          <img class="h-10 w-10 rounded-full" src="https://randomuser.me/api/portraits/men/32.jpg" alt="">
                        </div>
                        <div class="ml-4">
                          <div class="text-sm font-medium text-gray-900">Иванов Иван</div>
                        </div>
                      </div>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">Квартира, 3 комн., 85 м²</td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">Сидорова С.</td>
                    <td class="px-6 py-4 whitespace-nowrap">
                      <span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full bg-blue-100 text-blue-800">Проведен</span>
                    </td>
                    <td class="px-6 py-4 whitespace-nowrap text-sm font-medium">
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-edit"></i></a>
                      <a href="#" class="text-primary hover:text-red-700 mr-3"><i class="fas fa-eye"></i></a>
                      <a href="#" class="text-red-600 hover:text-red-900"><i class="fas fa-trash"></i></a>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
            <div class="px-6 py-4 border-t border-gray-200 flex items-center justify-between">
              <div class="text-sm text-gray-500">
                Показано <span class="font-medium">1</span> до <span class="font-medium">3</span> из
                <span class="font-medium">12</span> показов
              </div>
              <div class="flex space-x-2">
                <button class="px-3 py-1 border rounded text-gray-500 hover:bg-gray-50">Назад</button>
                <button class="px-3 py-1 border rounded bg-primary text-white hover:bg-red-800">1</button>
                <button class="px-3 py-1 border rounded text-gray-500 hover:bg-gray-50">2</button>

</html>
