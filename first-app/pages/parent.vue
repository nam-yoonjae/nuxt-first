<template>
    <div>
        <h2>Parent View</h2>
        <p>" Nested Pages " : 둥지, 감싼 페이지, 부모-자식 페이지</p>
        <p>parent.vue 파일은 template 내부에 NuxtChild 컴포넌트를 가지고 있다.</p>
        <p>(하위페이지를 안으려면 이 파일(parent.vue)과 같은 이름의 폴더(parent)가 있어야 하고 그안에 index.vue 가 있어야한다.)</p>
        <p>NuxtLink to 로 연결된 child vue 는 클릭 이벤트가 발생하면</p>
        <p>NuxtChild 태그 부분에 렌더링된다.</p>
        <nav>
            <ul>
                <li>
                    <NuxtLink to="/parent/child">Child 1</NuxtLink>
                </li>
                <li>
                    <NuxtLink to="/parent/child2">Child 2</NuxtLink>
                </li>
            </ul>
        </nav>
        <NuxtChild/>
    </div>
</template>
<style scoped>
ul {
  list-style: none;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 0;
}
li {
  margin: 0 0.5rem;
  padding: 0.25rem;
  font-size: 1rem;
}
</style>