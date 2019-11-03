<template>
    <div id="app">
        <v-app id="inspire">
            <div>
                <v-simple-table
                        :dense="dense"
                        :fixed-header="fixedHeader"
                        :height="height"
                >
                    <template v-slot:default>
                        <thead>
                        <tr>
                            <th class="text-left">Предметы</th>
                            <th class="text-left">Оценки</th>
                        </tr>
                        </thead>
                        <tbody>
                        <tr v-for="item in journal" :key="item.name">
                            <td>{{ item.student }}</td>
                            <td>{{ item.ball }}</td>
                        </tr>
                        </tbody>
                    </template>
                </v-simple-table>

            </div>
        </v-app>
    </div>
</template>

<script>
    export default {
        name: 'student_page',

        data: () => ({
            dense: false,
            fixedHeader: false,
            height: 300,
            journal: [
                {
                    student: 'Math',
                    ball: 76,
                },
                {
                    student: 'Russian language',
                    ball: 89,
                },
                {
                    student: 'Literature',
                    ball: 81,
                },
                {
                    student: 'Biology',
                    ball: 99,
                },
                {
                    student: 'Geography',
                    ball: 94,
                }
            ],
        }),
    }
</script>

