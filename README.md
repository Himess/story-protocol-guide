# Story ile İlk Adımlar: Hazırlık

Bu rehberde, Story protokolü üzerinde fikri mülkiyetinizi (IP) nasıl kaydedeceğinizi öğreneceksiniz. İlk adım, bilgisayarınızı ve gerekli araçları hazırlamak olacak.

## 1. Bir Çalışma Klasörü Oluşturun

Bilgisayarınızda bir klasör oluşturun. Örneğin: `StoryProject`. Bu klasörün içine tüm kodlarınızı ve dosyalarınızı ekleyeceğiz.

![image](https://github.com/user-attachments/assets/cc275a3e-386f-4832-8ba8-9281ee12be42)

---

## 2. Visual Studio Code (VS Code) Kurulumu

[VS Code](https://code.visualstudio.com/) web sitesine gidin ve işletim sisteminize uygun sürümü indirin.

1. İndirilen `.exe` dosyasını çalıştırın.
2. Lisans sözleşmesini kabul edin ve **Next** butonuna tıklayın.
3. Yükleme konumunu seçin (varsayılan yeri bırakabilirsiniz) ve **Next** butonuna tıklayın.
4. **Add to PATH** seçeneğini işaretleyin. Bu, VS Code'u terminalden çalıştırmanızı sağlar.
5. **Install** butonuna tıklayın ve kurulum tamamlanana kadar bekleyin.

Tebrikler, kurulum tamamlandı!

---

## 3. Gerekli Araçları Kurun

Story ile çalışmaya başlamak için aşağıdaki araçları bilgisayarınıza kurmanız gerekiyor:

### Node.js ve npm Kurulumu

[Node.js](https://nodejs.org/tr) web sitesine gidin ve **LTS (Long-Term Support)** sürümünü seçin.

![image](https://github.com/user-attachments/assets/e2a659e7-0c57-402a-a235-ffc3f00e39cb)

**Kurulum Adımları:**
1. İndirdiğiniz dosyayı çalıştırın.
2. Kurulumu **Next > Next** diyerek tamamlayın.
3. Ardından şu komutları terminale yazın ve çalıştırın:
   ```bash
   npm install -g ts-node
   npm install -g typescript

---

## 4. Visual Studio Code Uygulamasını Açın

Menüden File > Open Folder seçeneğine tıklayın ve oluşturduğunuz StoryProject adlı klasörü açın.

Daha sonra üst menüden Terminal > New Terminal seçeneğini tıklayın.

![image](https://github.com/user-attachments/assets/32ebc389-6810-488f-b05a-841e5c0d297e)

Node.js'in doğru şekilde yüklendiğini kontrol edin:

Terminale şu komutları yazın:
```bash
node -v
npm -v

Eğer şu şekilde çıktı alıyorsanız, kurulum başarılıdır:

![image](https://github.com/user-attachments/assets/9d39f4d7-0ce9-43fc-89ee-9412e2b99087)

---

## 5. Projeyi Başlatın

Aşağıdaki komutları çalıştırarak bir Node.js projesi başlatın:

```bash
npm init -y

Bu komut, projenizin kök dizininde bir 'package.json' dosyası oluşturur.

Örnek çıktı şu şekilde olmalıdır:

![image](https://github.com/user-attachments/assets/cda37400-2da5-4736-a1ec-14e0bb3561f3)

---

## 6. '.env' Dosyası Oluşturun

Proje klasörünüzde '.env' adında bir dosya oluşturun. Bu dosya, özel anahtarlarınızı ve hassas bilgilerinizi saklamak için kullanılacak.

Adımlar:
1-VS Code içinde sağ tıklayın ve New File seçeneğini seçin.
2-Dosya adını '.env' olarak yazın ve Enter tuşuna basın.
Şöyle görünecek:
![image](https://github.com/user-attachments/assets/9997e18c-85d1-4c64-a06c-bd4b52a73d03)

Sonuç şu şekilde olacaktır:
![image](https://github.com/user-attachments/assets/049c1b5b-6d18-497e-8764-d8f8d5b3e22d)

---

## 7. Testnet Cüzdan Özel Anahtarını Ekleyin

Story Testnet cüzdan özel anahtarınızı '.env' dosyasına ekleyin. Bu özel anahtar, Story ağına bağlantı kurmanızı sağlar.

Örnek:
```bash
WALLET_PRIVATE_KEY=<YOUR_WALLET_PRIVATE_KEY>
Not: Özel anahtarınızı asla başkasıyla paylaşmayın. Yeni bir cüzdan oluşturmanızı öneririm.

Örnek Çıktı:
```bash
WALLET_PRIVATE_KEY=e12312312312312312312312312312312312312312312312312312312312312

---

## 8. Pinata API Anahtarı Ekleyin

Pinata, IPFS ağına dosya yüklemek için kullanılan bir araçtır. Pinata üzerinden bir hesap oluşturun ve bir API Key (JWT) oluşturun.
https://app.pinata.cloud/developers/api-keys ' e girin.
+ New Key butonuna tıklayın.
Aşağıdaki kutucukları işaretleyin:

![image](https://github.com/user-attachments/assets/f64181c3-8c0d-445f-ab9f-a48d995a8533)

Verdiği JWT anahtarını kaydedin ve '.env' dosyanıza ekleyin:
```bash
PINATA_JWT=<YOUR_PINATA_JWT>

Örnek:
```bash
PINATA_JWT=e12321431242141424

---

## 9. '.env' Dosyasını Güncelleme

1-RPC URL'sini '.env' dosyasına ekleyin.
2-NFT Contract Adresi ekleyin.
```bash
RPC_PROVIDER_URL=https://rpc.odyssey.storyrpc.io
NFT_CONTRACT_ADDRESS=0x041B4F29183317Fd352AE57e331154b73F8a1D73

Final '.env' Örneği:
```bash
WALLET_PRIVATE_KEY=e12312312312312312312312312312312312312312312312312312312312312
PINATA_JWT=e12321431242141424
RPC_PROVIDER_URL=https://rpc.odyssey.storyrpc.io
NFT_CONTRACT_ADDRESS=0x041B4F29183317Fd352AE57e331154b73F8a1D73

---

## 10. Gerekli Paketleri Kurun

Terminalde aşağıdaki komutu çalıştırarak projeniz için gerekli bağımlılıkları yükleyin:
```bash
npm install @story-protocol/core-sdk pinata-web3 viem

Kurulum tamamlandığında dosyalarınız şu şekilde görünecek:

![image](https://github.com/user-attachments/assets/38737bb1-65db-447a-a7e2-93c10047889f)

---

## 11. Proje Dosyalarını Yapılandırma

Bu adımda, Story SDK'yı kullanmak ve IP verilerini oluşturmak için bazı temel dosyaları yapılandıracağız.

### 11.1 `utils.ts` Dosyasını Oluşturun

Bu dosya, Story SDK yapılandırmanızı (`config`) ve istemcinizi (`client`) kurmak için kullanılacak.

1. Proje kök dizininde **`utils.ts`** adında bir dosya oluşturun.
2. Aşağıdaki kodu dosyaya yapıştırın:

```typescript
import { StoryClient, StoryConfig } from '@story-protocol/core-sdk';
import { http } from 'viem';
import { privateKeyToAccount, Address, Account } from 'viem/accounts';

// Çevresel değişkenleri kontrol edin
const privateKey: Address = `0x${process.env.WALLET_PRIVATE_KEY}`;
if (!privateKey) {
  throw new Error('WALLET_PRIVATE_KEY bulunamadı. Lütfen .env dosyanızı kontrol edin.');
}

const account: Account = privateKeyToAccount(privateKey);

const config: StoryConfig = {
  account: account,
  transport: http(process.env.RPC_PROVIDER_URL),
  chainId: 'odyssey',
};

const client = StoryClient.newClient(config);

export { client, account };

Sonuç şu şekilde görünecek:

![image](https://github.com/user-attachments/assets/6957e055-ab6a-45a3-9e04-95d52ce9f6b2)

---

## 11.2 Metadata Dosyalarını Ayarlayın

IP ve NFT metadata bilgilerini oluşturacağız.

Proje kök dizininde 'main.ts' adında bir dosya oluşturun.
Aşağıdaki kodu dosyaya yapıştırın:

```typescript
import { IpMetadata } from '@story-protocol/core-sdk';
import { client, account } from './utils';
import { uploadJSONToIPFS } from './uploadToIpfs';
import { createHash } from 'crypto';
import { Address } from 'viem';
import { mintNFT } from './mintNFT';

async function main() {
  // 1. IP Metadata oluştur
  const ipMetadata: IpMetadata = client.ipAsset.generateIpMetadata({
    title: 'My IP Asset',
    description: 'This is a test IP asset',
    watermarkImg: 'https://picsum.photos/200',
    attributes: [
      {
        key: 'Rarity',
        value: 'Legendary',
      },
    ],
  });

  // 2. NFT Metadata oluştur
  const nftMetadata = {
    name: 'Ownership NFT',
    description: 'This is an NFT representing ownership of our IP Asset.',
    image: 'https://picsum.photos/200',
  };

  // 3. Metadata'ları IPFS'e yükle
  const ipIpfsHash = await uploadJSONToIPFS(ipMetadata);
  const ipHash = createHash('sha256').update(JSON.stringify(ipMetadata)).digest('hex');
  const nftIpfsHash = await uploadJSONToIPFS(nftMetadata);
  const nftHash = createHash('sha256').update(JSON.stringify(nftMetadata)).digest('hex');

  console.log('IP Metadata IPFS Hash:', ipIpfsHash);
  console.log('NFT Metadata IPFS Hash:', nftIpfsHash);

  // 4. NFT Mint Et
  const tokenId = await mintNFT(account.address, `https://ipfs.io/ipfs/${nftIpfsHash}`);
  if (!tokenId) {
    console.error('NFT mint işlemi başarısız oldu!');
    return;
  }

  console.log('Mint edilen NFT Token ID:', tokenId);

  // 5. NFT'yi IP Asset olarak kaydet
  const response = await client.ipAsset.registerIpAndAttachPilTerms({
    nftContract: process.env.NFT_CONTRACT_ADDRESS as Address,
    tokenId: tokenId,
    terms: [], // Özel IP şartlarını buraya ekleyebilirsiniz.
    ipMetadata: {
      ipMetadataURI: `https://ipfs.io/ipfs/${ipIpfsHash}`,
      ipMetadataHash: `0x${ipHash}`,
      nftMetadataURI: `https://ipfs.io/ipfs/${nftIpfsHash}`,
      nftMetadataHash: `0x${nftHash}`,
    },
    txOptions: { waitForTransaction: true },
  });

  console.log(`Transaction Hash: ${response.txHash}`);
  console.log(`IP Asset ID: ${response.ipId}`);
  console.log(`View on Explorer: https://explorer.story.foundation/ipa/${response.ipId}`);
}

main().catch((error) => {
  console.error('Bir hata oluştu:', error);
});

---

## 11.3 'uploadToIpfs.ts' Dosyasını Oluşturun
Proje kök dizininde 'uploadToIpfs.ts' adında bir dosya oluşturun.
Aşağıdaki kodu dosyaya yapıştırın:

```typescript
import { PinataSDK } from 'pinata-web3';

const pinata = new PinataSDK({
  pinataJwt: process.env.PINATA_JWT,
});

export async function uploadJSONToIPFS(jsonMetadata: any): Promise<string> {
  const { IpfsHash } = await pinata.upload.json(jsonMetadata);
  return IpfsHash;
}

---

## 11.4 TypeScript ve tsconfig.json Ayarları

Proje dizininizde bir 'tsconfig.json' dosyası oluşturun. İçerisine aşağıdaki ayarları ekleyin:

```json
{
  "compilerOptions": {
    "target": "ES6",
    "module": "CommonJS",
    "strict": true,
    "esModuleInterop": true,
    "moduleResolution": "node",
    "baseUrl": "./",
    "paths": {
      "*": ["node_modules/*"]
    }
  },
  "include": ["**/*.ts"],
  "exclude": ["node_modules"]
}

Sonuç şu şekilde görünmeli:
![image](https://github.com/user-attachments/assets/c06ddcb0-23a5-475b-a254-f53e6239d909)

---

## 12. Mint Fonksiyonunu Tanımlayın
Proje kök dizininde 'mintNFT.ts' adlı bir dosya oluşturun ve aşağıdaki kodları ekleyin:

```typescript
import { http, createWalletClient, createPublicClient, Address } from 'viem';
import { privateKeyToAccount } from 'viem/accounts';
import { odyssey } from '@story-protocol/core-sdk';
import { account } from './utils';
import { defaultNftContractAbi } from './defaultNftContractAbi';

const baseConfig = {
  chain: odyssey,
  transport: http(process.env.RPC_PROVIDER_URL),
} as const;

export const publicClient = createPublicClient(baseConfig);
export const walletClient = createWalletClient({
  ...baseConfig,
  account,
});

export async function mintNFT(to: Address, uri: string): Promise<number | undefined> {
  const { request } = await publicClient.simulateContract({
    address: process.env.NFT_CONTRACT_ADDRESS as Address,
    functionName: 'mintNFT',
    args: [to, uri],
    abi: defaultNftContractAbi,
  });
  const hash = await walletClient.writeContract(request);
  const { logs } = await publicClient.waitForTransactionReceipt({
    hash,
  });
  if (logs[0].topics[3]) {
    return parseInt(logs[0].topics[3], 16);
  }
}

---

## 13. 'defaultNftContractAbi.ts' Dosyasını Oluşturun

Proje kök dizininde 'defaultNftContractAbi.ts' adında bir dosya oluşturun ve aşağıdaki kodu yapıştırın:

```typescript
export const defaultNftContractAbi = [
  {
    inputs: [
      {
        internalType: "address",
        name: "to",
        type: "address",
      },
      {
        internalType: "string",
        name: "uri",
        type: "string",
      },
    ],
    name: "mintNFT",
    outputs: [
      {
        internalType: "uint256",
        name: "tokenId",
        type: "uint256",
      },
    ],
    stateMutability: "nonpayable",
    type: "function",
  },
];

---

## 14. Projeyi Çalıştırma

Tüm dosyaları oluşturduktan sonra, projeyi terminalde çalıştırmak için aşağıdaki komutu kullanın:

```bash
ts-node main.ts

**Örnek Çıktı**
Projeyi başarıyla çalıştırdıktan sonra aşağıdaki gibi bir çıktı almalısınız:

IP Metadata IPFS Hash: bafkreibyrubc2hy4nycjshqws55rwrfg7uclivodyzcmxwwqh3jzfgkzca
NFT Metadata IPFS Hash: bafkreigzbzrvl5wry755hmpr4qmnm5yucjaxp4to46v6yfq73q7bsc4p5q
Mint Edilen NFT Token ID: 440
Transaction Hash: 0x22d1c50e14bf525e375747fa79b56ee2320e59a0497f2902911a99364ab6dd27
IP Asset ID: 0x872EA5aA2FFa5b32c7f653Bf1bae7150B80AE041
https://explorer.story.foundation/ipa/0x872EA5aA2FFa5b32c7f653Bf1bae7150B80AE041

**Tebrikler! 🎉**
Projeyi başarıyla tamamladınız ve IP Asset oluşturmayı başardınız. Artık kendi IP varlıklarınızı Story Protocol üzerinde kaydedip yönetebilirsiniz!
