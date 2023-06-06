# Условие

Необходимо реализовать виртуальный скроллинг для списка из большого количества элементов фиксированного размера.

Нужно релизовать компоненту `Viewport` и `VirtualList`, используются они вот так:
```typescript
<Viewport height={900}>
    <VirtualList elements={elements} />
</Viewport>
```

где `elements: VirtualElement[]`
```typescript
interface VirtualElement {
    height: number;
    id: string;
}
```

Компонента `Viewport` должна задавать размеры вьюпорта (через нее смотрим на элементы).
Компонента `VirtualList` нужно для вывода элементов, она спрашивает размеры вьюпорта (мб через контекст).

Проще всего реализовать скроллинг как сделано в [height.app](height.app), там `VirtualList` это огромный `div`, в котором елементы выводятся через
`position: absolute`.
