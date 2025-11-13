
    <section class="bg-white w-80 p-6 rounded-xl shadow-lg">
        <h1 class="text-2xl font-semibold text-center text-gray-800 mb-4">
            To-Do List
        </h1>

        <form id="todo-form" class="flex gap-2 mb-4">
      
            <input 
                type="text" 
                id="new-task" 
                placeholder="Zadej nový úkol..."
                required
                class="flex-1 border border-gray-300 rounded-lg px-3 py-2 text-sm focus:outline-none focus:ring-2 focus:ring-blue-500"
            >

            <button 
                type="submit"
                class="bg-blue-600 text-white px-4 py-2 rounded-lg hover:bg-blue-700 transition-colors"
                >
                Přidat
            </button>

        </form>

        <ul id="task-list" class="space-y-2">
            <li class="bg-gray-50 border border-gray-200 rounded-lg px-3 py-2">Umýt nádobí</li>
            <li class="bg-gray-50 border border-gray-200 rounded-lg px-3 py-2">Zacvičit si</li>
        </ul>

    </section>



