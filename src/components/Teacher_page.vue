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
                            <th class="text-left">Учащиеся</th>
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
        name: 'teacher_page',

        data: () => ({
            dense: false,
            fixedHeader: false,
            height: 300,
            journal: [
                {
                    student: 'Kolya',
                    ball: 65,
                },
                {
                    student: 'Dmitriu',
                    ball: 88,
                },
                {
                    student: 'Alexandre',
                    ball: 56,
                },
                {
                    student: 'Evgeniy',
                    ball: 67,
                },
                {
                    student: 'Anastacia',
                    ball: 72,
                }
            ],
        }),
    }
</script>

