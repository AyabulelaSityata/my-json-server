<template>
    <div id="student_data">

    </div>
</template>

<script>
    async function getUsers() {
        const students = await fetch("https://github.com/AyabulelaSityata/my-json-server.git");
        const data = await students.json()
        let fetchedData = data.students

        const display = document.querySelector('#student_data')

        fetchedData.forEach(students =>{
            display.innerHTML +=`
            <div>
                <div class="student-body">
                    <h3>${students.firstName}</h3>
                    <p>${students.lastName}</p>
                    <p>${students.age}</p>
                </div>
            </div>`
        })
    }
    getUsers()
</script>

<style scoped>

</style>