# 📊 Modelos de Dados

## 🎲 Jogo (Game)

```typescript
interface Game {
  id: string;
  name: string;
  description: string;
  minPlayers: number;
  maxPlayers: number;
  playTime: {
    min: number;
    max: number;
  };
  ageRating: number;
  categories: string[];
  tags: string[];
  complexity: 'Fácil' | 'Médio' | 'Complexo';
  language: string[];
  publisher: string;
  releaseYear: number;
  stock: {
    total: number;
    available: number;
    maintenance: number;
  };
  pricing: {
    daily: number;
    threeDays: number;
    fiveDays: number;
  };
  images: {
    thumbnail: string;
    cover: string;
    gallery: string[];
  };
  rating: {
    average: number;
    count: number;
  };
  status: 'Disponível' | 'Indisponível' | 'Manutenção';
  createdAt: Timestamp;
  updatedAt: Timestamp;
}
```

## 👤 Usuário (User)

```typescript
interface User {
  id: string;
  name: string;
  email: string;
  phone: string;
  address: {
    street: string;
    number: string;
    complement?: string;
    neighborhood: string;
    city: string;
    state: string;
    zipCode: string;
  };
  documents: {
    cpf: string;
    rg?: string;
  };
  profilePicture?: string;
  role: 'cliente' | 'admin' | 'gerente';
  status: 'ativo' | 'inativo' | 'bloqueado';
  preferences: {
    favoriteGames: string[];
    favoriteCategories: string[];
    notifications: boolean;
  };
  membership?: {
    plan: 'basic' | 'premium';
    startDate: Timestamp;
    endDate: Timestamp;
  };
  createdAt: Timestamp;
  updatedAt: Timestamp;
}
```

## 📝 Aluguel (Rental)

```typescript
interface Rental {
  id: string;
  userId: string;
  gameId: string;
  status: 'pendente' | 'confirmado' | 'em_andamento' | 'concluído' | 'cancelado';
  period: {
    type: '1_day' | '3_days' | '5_days';
    startDate: Timestamp;
    endDate: Timestamp;
  };
  pricing: {
    basePrice: number;
    discount?: number;
    total: number;
  };
  payment: {
    status: 'pendente' | 'aprovado' | 'recusado';
    method: 'credit_card' | 'pix' | 'cash';
    transactionId?: string;
  };
  delivery?: {
    type: 'pickup' | 'delivery';
    address?: Address;
    status: 'pendente' | 'em_rota' | 'entregue';
    trackingCode?: string;
  };
  checklist: {
    pickup: {
      pieces: boolean;
      manual: boolean;
      damages: string[];
      photos: string[];
    };
    return: {
      pieces: boolean;
      manual: boolean;
      damages: string[];
      photos: string[];
    };
  };
  rating?: {
    score: number;
    comment: string;
    createdAt: Timestamp;
  };
  createdAt: Timestamp;
  updatedAt: Timestamp;
}
```

## ⭐ Avaliação (Review)

```typescript
interface Review {
  id: string;
  gameId: string;
  userId: string;
  rentalId: string;
  rating: number;
  comment: string;
  likes: number;
  photos?: string[];
  status: 'pendente' | 'aprovado' | 'rejeitado';
  moderation?: {
    moderatorId: string;
    reason?: string;
    date: Timestamp;
  };
  createdAt: Timestamp;
  updatedAt: Timestamp;
}
```

## 🏷️ Categoria (Category)

```typescript
interface Category {
  id: string;
  name: string;
  description: string;
  icon: string;
  slug: string;
  parentId?: string;
  status: 'ativo' | 'inativo';
  createdAt: Timestamp;
  updatedAt: Timestamp;
}
```

## 🎯 Promoção (Promotion)

```typescript
interface Promotion {
  id: string;
  name: string;
  description: string;
  type: 'percentage' | 'fixed_value';
  value: number;
  code?: string;
  conditions: {
    minRentalDays?: number;
    minValue?: number;
    categories?: string[];
    games?: string[];
    userType?: string[];
  };
  validity: {
    startDate: Timestamp;
    endDate: Timestamp;
  };
  usage: {
    limit?: number;
    used: number;
  };
  status: 'ativo' | 'inativo' | 'expirado';
  createdAt: Timestamp;
  updatedAt: Timestamp;
}
```

## 📊 Relatório (Report)

```typescript
interface Report {
  id: string;
  type: 'daily' | 'weekly' | 'monthly';
  period: {
    startDate: Timestamp;
    endDate: Timestamp;
  };
  metrics: {
    totalRentals: number;
    revenue: number;
    newUsers: number;
    activeGames: number;
    popularGames: {
      gameId: string;
      rentals: number;
    }[];
    categories: {
      categoryId: string;
      rentals: number;
    }[];
  };
  status: 'processando' | 'completo' | 'erro';
  createdAt: Timestamp;
  updatedAt: Timestamp;
}
```

## 🔔 Notificação (Notification)

```typescript
interface Notification {
  id: string;
  userId: string;
  type: 'rental' | 'return' | 'promotion' | 'system';
  title: string;
  message: string;
  data?: {
    rentalId?: string;
    gameId?: string;
    promotionId?: string;
  };
  status: 'não_lida' | 'lida';
  priority: 'baixa' | 'média' | 'alta';
  createdAt: Timestamp;
  expiresAt?: Timestamp;
}
```

## 🛠️ Manutenção (Maintenance)

```typescript
interface Maintenance {
  id: string;
  gameId: string;
  type: 'preventiva' | 'corretiva';
  description: string;
  status: 'pendente' | 'em_andamento' | 'concluída' | 'cancelada';
  technician?: {
    id: string;
    name: string;
  };
  issues: {
    description: string;
    severity: 'baixa' | 'média' | 'alta';
    photos?: string[];
  }[];
  cost?: number;
  startDate: Timestamp;
  endDate?: Timestamp;
  notes?: string;
  createdAt: Timestamp;
  updatedAt: Timestamp;
}
```

## 📱 Dispositivo (Device)

```typescript
interface Device {
  id: string;
  userId: string;
  type: 'ios' | 'android' | 'web';
  token: string;
  name?: string;
  model?: string;
  lastAccess: Timestamp;
  status: 'ativo' | 'inativo';
  createdAt: Timestamp;
  updatedAt: Timestamp;
}
``` 