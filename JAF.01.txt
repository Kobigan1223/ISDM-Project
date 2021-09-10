-- Table structure for table user_credentials
--

CREATE TABLE user_credentials (
  userId varchar(20) NOT NULL,
  email varchar(255) NOT NULL PRIMARY KEY,
  password varchar(255) NOT NULL
) 

--
-- INSERT data for table user_credentials
--


INSERT INTO user_credentials VALUES ('SOW003', 'asdfg@gmail.com', 'asdf@charlie');
INSERT INTO user_credentials VALUES ('CMR007', 'fafagah@gmail.com', '12345');
INSERT INTO user_credentials VALUES ('CMR002', 'henrykpape@gmail.com', 'HenryK@charlie');
INSERT INTO user_credentials VALUES ('CMR003', 'jackkirby@gmail.com', 'JackK@charlie');
INSERT INTO user_credentials VALUES ('CMR005', 'joerusso@gmail.com', 'JoeR@charlie');
INSERT INTO user_credentials VALUES ('SOW004', 'john@gmail.com', 'john@charlie');
INSERT INTO user_credentials VALUES ('CMR008', 'kobigan@gmail.com', '123456');
INSERT INTO user_credentials VALUES ('CMR009', 'kobigank@gmail.com', '123456');
INSERT INTO user_credentials VALUES ('CMR006', 'kumaransathiyavarathan@gmail.com', 'kumaran14');
INSERT INTO user_credentials VALUES ('SOW001', 'Michael@gmail.com', 'Michael@charlie');
INSERT INTO user_credentials VALUES ('SOW002', 'Robert@gmail.com', 'Robert@charlie');
INSERT INTO user_credentials VALUES ('SOW005', 'will@gmail.com', 'will@charlie');
INSERT INTO user_credentials VALUES ('CMR001', 'william@gmail.com', 'William@charlie');

-- --------------------------------------------------------

--
-- Table structure for table user_details
--

CREATE TABLE user_details (
  userId varchar(20) NOT NULL PRIMARY KEY,
  userName varchar(255) NOT NULL,
  profImgLoc varchar(255) NOT NULL DEFAULT '../images/userprofpics/no_avatar.jpg',
  mob_no varchar(20) DEFAULT NULL,
  address varchar(500) DEFAULT NULL,FOREIGN KEY (userId) REFERENCES user_details (userId)
) 

--
-- INSERT data for table user_details
--


INSERT INTO user_details VALUES ('CMR001', 'William Turner', '../images/userprofpics/CMR001.jpg', '0771234667', '177A Bleecker Street, Manhattan.');
INSERT INTO user_details VALUES ('CMR002', 'Henry K Pape', '../images/userprofpics/CMR002.jpg', '0212222254', '2058  Cambridge Court,Russellville');
INSERT INTO user_details VALUES ('CMR003', 'Jack Kirby', '../images/userprofpics/CMR003.jpg', '1452365899', '711  Long Street,Brooksville');
INSERT INTO user_details VALUES ('CMR004', 'Joe Russo', '../images/userprofpics/no_avatar.jpg', '5698569885', 'no address');
INSERT INTO user_details VALUES ('CMR005', 'Joe Russo', '../images/userprofpics/no_avatar.jpg', NULL, NULL);
INSERT INTO user_details VALUES ('CMR006', 'Kumaran', '../images/userprofpics/no_avatar.jpg', '0751231564', 'kopay');
INSERT INTO user_details VALUES ('CMR007', 'addada', '../images/userprofpics/no_avatar.jpg', NULL, NULL);
INSERT INTO user_details VALUES ('CMR008', 'kobigan', '../images/userprofpics/no_avatar.jpg', NULL, NULL);
INSERT INTO user_details VALUES ('CMR009', 'kobigan15', '../images/userprofpics/no_avatar.jpg', NULL, NULL);
INSERT INTO user_details VALUES ('SOW001', 'Michael B Jordan', '../images/userprofpics/SOW001.jpg', '0772563654', '177A Bleecker Street, Greenwich Village, Manhattan');
INSERT INTO user_details VALUES ('SOW002', 'Robert Downey, Jr.', '../images/userprofpics/SOW002.jpg', '0772563985', 'Malibu Point 10880, 90265,Malibu, California.');
INSERT INTO user_details VALUES ('SOW003', 'kkkkk', '../images/userprofpics/no_avatar.jpg', '012254588', 'ggghfghfhgfhf');
INSERT INTO user_details VALUES ('SOW004', 'ghgj', '../images/userprofpics/no_avatar.jpg', NULL, NULL);
INSERT INTO user_details VALUES ('SOW005', 'fgfghhh', '../images/userprofpics/no_avatar.jpg', NULL, NULL);


-- Table structure for table product_category


CREATE TABLE product_category (
  categoryid varchar(20) NOT NULL PRIMARY KEY,
  categoryName varchar(255) NOT NULL
) 

--
-- INSERT data for table product_category
--


INSERT INTO product_category VALUES ('CAT001', 'Mobile Phone');
INSERT INTO product_category VALUES ('CAT002', 'Electronics');
INSERT INTO product_category VALUES ('CAT007', 'grocery');
INSERT INTO product_category VALUES ('CAT005', 'Home Products');
INSERT INTO product_category VALUES ('CAT006', 'kids fashion');
INSERT INTO product_category VALUES ('CAT004', 'Men''s Fashion');
INSERT INTO product_category VALUES ('CAT003', 'Women''s Fashion');
 --
-- Table structure for table product_details
--

CREATE TABLE product_details (
  productid varchar(20) NOT NULL PRIMARY KEY,
  productName varchar(255) NOT NULL,
  productPrice decimal(20,2) NOT NULL,
  productQty INTEGER NOT NULL,
  productCat varchar(20) NOT NULL,
  productDescription varchar(1000) NOT NULL,
  productImage1Loc varchar(255) DEFAULT '../images/Products/noimage.jpg',
  productImage2Loc varchar(255) DEFAULT '../images/Products/noimage.jpg',
  productImage3Loc varchar(255) DEFAULT '../images/Products/noimage.jpg',
  productImage4Loc varchar(255) DEFAULT '../images/Products/noimage.jpg',
  availability varchar(20) NOT NULL DEFAULT 'Available' ,
  FOREIGN KEY (productCat) REFERENCES product_category (categoryid)
  )
  

-- INSERT data for table product_details
--

INSERT INTO product_details VALUES ('PRD001', 'Note20 Ultra', '260000.00', 25, 'CAT001', 'Released 2020, August 21 , 208g, 8.1mm thickness, Android 10, One UI 2.5, 128GB/256GB/512GB storage, microSDXC', '../images/Products/PRD001/img1.jpg', '../images/Products/PRD001/img2.jpg', '../images/Products/PRD001/img3.jpg', '../images/Products/PRD001/img4.jpg', DEFAULT);
INSERT INTO product_details VALUES ('PRD002', 'Galaxy S7 Edge', '55000.00', 50, 'CAT001', 'Released 2020, August 21 , 208g, 8.1mm thickness, Android 10, One UI 2.5, 128GB/256GB/512GB storage, microSDXC', '../images/Products/PRD002/img1.jpg', '../images/Products/PRD002/img2.jpg', '../images/Products/PRD002/img3.jpg', '../images/Products/PRD002/img4.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD003', 'Keyboard', '1200.00', 15, 'CAT002', 'Released 2020, August 21, 208g, 8.1mm thickness , Android 10, One UI 2.5 128GB/256GB/512GB storage, microSDXC', '../images/Products/PRD003/img1.jpg', '../images/Products/PRD003/img2.jpg', '../images/Products/PRD003/img3.jpg', '../images/Products/PRD003/img4.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD004', 'Screen protector', '700.00', 45, 'CAT001', 'Released 2020, August 21, 208g, 8.1mm thickness, Android 10, One UI 2.5, 128GB/256GB/512GB storage,, microSDXC', '../images/Products/PRD004/img1.jpg', '../images/Products/PRD004/img2.jpg', '../images/Products/PRD004/img3.jpg', '../images/Products/PRD004/img4.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD005', 'iPhone XS Max', '250000.00', 56, 'CAT001', 'Released 2020, August 21, 208g, 8.1mm thickness, Android 10, One UI 2.5, 128GB/256GB/512GB storage,, microSDXC', '../images/Products/PRD005/img1.jpg', '../images/Products/PRD005/img2.jpg', '../images/Products/PRD005/img3.jpg', '../images/Products/PRD005/img4.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD006', 'Mouse', '1500.00', 15, 'CAT002', 'Released 2020, August 21, 208g, 8.1mm thickness, Android 10, One UI 2.5, 128GB/256GB/512GB storage,, microSDXC', '../images/Products/PRD006/img1.jpg', '../images/Products/PRD006/img2.jpg', '../images/Products/PRD006/img3.jpg', '../images/Products/PRD006/img4.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD007', 'LG Wing 5G', '92138.00', 20, 'CAT001', 'Released 2020, August 21, 208g, 8.1mm thickness, Android 10, One UI 2.5, 128GB/256GB/512GB storage,, microSDXC', '../images/Products/PRD007/img1.jpg', '../images/Products/PRD007/img2.jpg', '../images/Products/PRD007/img3.jpg', '../images/Products/PRD007/img4.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD008', 'Galaxy S20', '125000.00', 42, 'CAT001', 'Released 2020, August 21, 208g, 8.1mm thickness, Android 10, One UI 2.5, 128GB/256GB/512GB storage,, microSDXC', '../images/Products/PRD008/img1.jpg', '../images/Products/PRD008/img2.jpg', '../images/Products/PRD008/img3.jpg', '../images/Products/PRD008/img4.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD009', 'Samsung phone', '80000.00', 21, 'CAT001', '208g, 8.1mm thickness, Android 10, One UI 2.5, 128GB/256GB/512GB storage,, microSDXC', '../images/Products/PRD009/img1.jpg', '../images/Products/PRD009/img2.jpg', '../images/Products/PRD009/img3.jpg', '../images/Products/PRD009/img4.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD010', 'Fridge', '50000.00', 5, 'CAT002', 'ffghhjjk', '../images/Products/PRD010/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD011', 'dell laptop', '200000.00', 5, 'CAT002', 'laptops', '../images/Products/PRD011/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD012', 'HP laptops', '100000.00', 4, 'CAT002', 'laptops', '../images/Products/PRD012/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD013', 'washing machine', '30000.00', 10, 'CAT002', 'washing machine ', '../images/Products/PRD013/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD014', 'Hair Dryer', '10000.00', 3, 'CAT002', 'drying', '../images/Products/PRD014/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD015', 'mixer', '5000.00', 5, 'CAT002', 'cake mixer', '../images/Products/PRD015/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD016', 'Rice cookers', '5000.00', 6, 'CAT003', 'rice cookers', '../images/Products/PRD016/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD017', 'Blue shirt', '1200.00', 5, 'CAT004', 'reerwe', '../images/Products/PRD017/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD018', 'Denim shirt', '1000.00', 5, 'CAT004', 'eteyyr', '../images/Products/PRD018/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD019', 'White and Blue shirt', '1000.00', 3, 'CAT004', 'wetete', '../images/Products/PRD019/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD020', 'blue and ash dress', '1500.00', 5, 'CAT003', 'retreyeye', '../images/Products/PRD020/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD021', 'Yellow dress', '1200.00', 6, 'CAT003', 're6ri', '../images/Products/PRD021/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD022', 'ladies black frock', '2000.00', 5, 'CAT003', 'aewrre', '../images/Products/PRD022/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD023', 'lady jeans', '2000.00', 5, 'CAT003', 'reyru', '../images/Products/PRD023/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD024', 'red frock', '1500.00', 5, 'CAT003', 'sartsye', '../images/Products/PRD024/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD025', 'green dress', '500.00', 2, 'CAT003', 'ghggh', '../images/Products/PRD025/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD026', 'frock green', '1500.00', 2, 'CAT003', 'r6ee7', '../images/Products/PRD026/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD027', 'yellow frock', '500.00', 5, 'CAT003', 'drtesryduf', '../images/Products/PRD027/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD028', 'blue dress', '500.00', 5, 'CAT003', 'fsegh', '../images/Products/PRD028/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD029', 'red dress', '500.00', 5, 'CAT003', 'reyeey', '../images/Products/PRD029/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD030', 'yellow top', '1200.00', 5, 'CAT003', 'aarer', '../images/Products/PRD030/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD031', 'blue top', '1000.00', 5, 'CAT003', 'fdffsd', '../images/Products/PRD031/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD032', 'purple top', '1200.00', 5, 'CAT003', 'eafefefef', '../images/Products/PRD032/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD033', 'chair', '5000.00', 5, 'CAT005', 'asdfaf', '../images/Products/PRD033/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD034', 'easy chair', '4500.00', 2, 'CAT005', 'dafdfdfdf', '../images/Products/PRD034/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD035', 'matress', '2000.00', 5, 'CAT005', 'dsddddsd', '../images/Products/PRD035/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD036', 'set chairs', '15000.00', 5, 'CAT005', 'sdsdsd', '../images/Products/PRD036/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD037', 'little table', '5000.00', 4, 'CAT005', 'ewtttrtt', '../images/Products/PRD037/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD038', 'Bed and mattress', '20000.00', 5, 'CAT005', 'jsshhs', '../images/Products/PRD038/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD039', 'single chair', '5000.00', 6, 'CAT005', 'ajhjgdsj', '../images/Products/PRD039/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD040', 'chair and table', '7000.00', 7, 'CAT005', 'jjhhjhssa', '../images/Products/PRD040/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD041', 'wall hanger', '5000.00', 7, 'CAT005', 'hhshjhj', '../images/Products/PRD041/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD042', 'small table', '5000.00', 5, 'CAT005', 'hdhhdhh', '../images/Products/PRD042/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD043', 'chair with bed', '5000.00', 2, 'CAT005', 'ajjaff', '../images/Products/PRD043/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD044', 'study chair', '2000.00', 5, 'CAT005', 'ggggg', '../images/Products/PRD044/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD045', 'one small table ', '5000.00', 5, 'CAT005', 'hshsh', '../images/Products/PRD045/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD046', 'one easy chair', '2000.00', 5, 'CAT005', 'sdsdsds', '../images/Products/PRD046/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD047', 'tea stand', '2500.00', 5, 'CAT005', 'shshhss', '../images/Products/PRD047/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD048', 'big chair', '5000.00', 5, 'CAT005', 'ssggsgs', '../images/Products/PRD048/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD049', 'soya sticks', '200.00', 5, 'CAT007', 'setrtryry', '../images/Products/PRD049/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD050', 'oreo', '150.00', 10, 'CAT007', 'sfsryry', '../images/Products/PRD050/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD051', 'welch', '50.00', 5, 'CAT007', 'fsdfs', '../images/Products/PRD051/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD052', 'lays', '50.00', 5, 'CAT007', 'dstydt', '../images/Products/PRD052/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD053', 'salt', '50.00', 12, 'CAT007', 'dasddg', '../images/Products/PRD053/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD054', 'salt packets', '20.00', 5, 'CAT007', 'stttsr', '../images/Products/PRD054/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD055', 'lays blue', '55.00', 5, 'CAT007', 'ewarr', '../images/Products/PRD055/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD056', 'mixture', '100.00', 5, 'CAT007', 'ddftsff', '../images/Products/PRD056/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD057', 'doritos', '200.00', 10, 'CAT007', 'dewrtyeu', '../images/Products/PRD057/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD058', 'soya sticks', '50.00', 5, 'CAT007', 'etreyy', '../images/Products/PRD058/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD059', 'fritos', '200.00', 5, 'CAT007', 'hsdhhfds', '../images/Products/PRD059/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD060', 'tea packet', '210.00', 5, 'CAT007', 'hjdhjsf', '../images/Products/PRD060/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD061', 'rice', '500.00', 5, 'CAT007', 'hjshdsd', '../images/Products/PRD061/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD062', 'dalia', '55.00', 5, 'CAT007', 'tyiy', '../images/Products/PRD062/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD063', 'tea', '55.00', 5, 'CAT007', 'tdytuti', '../images/Products/PRD063/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD064', 'food colors', '50.00', 5, 'CAT007', 'dfsdgs', '../images/Products/PRD064/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD065', 'boy kid dress', '2000.00', 5, 'CAT007', 'gggghh', '../images/Products/PRD065/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD066', 'girl kid dress', '2500.00', 5, 'CAT006', 'gfghg', '../images/Products/PRD066/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD067', 'baby chair', '1500.00', 5, 'CAT006', 'ghghghgh', '../images/Products/PRD067/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD068', 'little kid chair', '2500.00', 6, 'CAT006', 'ftrti', '../images/Products/PRD068/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD069', 'kids cycle', '5000.00', 6, 'CAT006', 'te7rtyy', '../images/Products/PRD069/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD070', 'panadol syrub', '200.00', 12, 'CAT006', 'sssddd', '../images/Products/PRD070/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD071', 'kids basket', '2000.00', 5, 'CAT006', 'wetwt', '../images/Products/PRD071/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD072', 'kids building toys', '2000.00', 5, 'CAT006', 'sfaffssr', '../images/Products/PRD072/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD073', 'kids bag', '1200.00', 6, 'CAT006', 'kids bag', '../images/Products/PRD073/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD074', 'kids food basket', '100.00', 5, 'CAT006', 'kids food basket', '../images/Products/PRD074/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD075', 'cartoon kid bag', '1200.00', 5, 'CAT006', 'cartoon kid bag', '../images/Products/PRD075/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD076', 'baby bag', '1000.00', 12, 'CAT006', 'baby bag', '../images/Products/PRD076/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD077', 'kid chair little', '2000.00', 5, 'CAT006', 'kid chair little', '../images/Products/PRD077/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD078', 'kid pencil box', '120.00', 5, 'CAT006', 'kid pencil box', '../images/Products/PRD078/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD079', 'kid study box', '200.00', 5, 'CAT006', 'kid study box', '../images/Products/PRD079/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');
INSERT INTO product_details VALUES ('PRD080', 'kid bero', '5000.00', 2, 'CAT006', 'kid bero', '../images/Products/PRD080/img1.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', '../images/Products/noimage.jpg', 'Available');

-- --------------------------------------------------------


-- Table structure for table product_color

CREATE TABLE product_color (
  productid varchar(20) NOT NULL,
  color varchar(255) NOT NULL,  PRIMARY KEY(productid,color),
  FOREIGN KEY (productid) REFERENCES product_details (productid)
) 

--
-- INSERT data for table product_color
--


INSERT INTO product_color VALUES ('PRD001', 'blue');
INSERT INTO product_color VALUES ('PRD001', 'gold');
INSERT INTO product_color VALUES ('PRD001', 'red');
INSERT INTO product_color VALUES ('PRD001', 'white');
INSERT INTO product_color VALUES ('PRD002', 'black');
INSERT INTO product_color VALUES ('PRD002', 'white');
INSERT INTO product_color VALUES ('PRD003', 'black');
INSERT INTO product_color VALUES ('PRD003', 'rgb');
INSERT INTO product_color VALUES ('PRD004', 'black');
INSERT INTO product_color VALUES ('PRD004', 'white');
INSERT INTO product_color VALUES ('PRD005', 'black');
INSERT INTO product_color VALUES ('PRD005', 'gold');
INSERT INTO product_color VALUES ('PRD005', 'red');
INSERT INTO product_color VALUES ('PRD005', 'white');
INSERT INTO product_color VALUES ('PRD006', 'blue');
INSERT INTO product_color VALUES ('PRD006', 'grey');
INSERT INTO product_color VALUES ('PRD007', 'blue');
INSERT INTO product_color VALUES ('PRD007', 'red');
INSERT INTO product_color VALUES ('PRD008', 'blue');
INSERT INTO product_color VALUES ('PRD008', 'pink');
INSERT INTO product_color VALUES ('PRD008', 'red');
INSERT INTO product_color VALUES ('PRD009', 'black');
INSERT INTO product_color VALUES ('PRD009', 'blue');
INSERT INTO product_color VALUES ('PRD010', 'silver');
INSERT INTO product_color VALUES ('PRD010', 'white');

-- --------------------------------------------------------


-- Table structure for table product_keywords
--

CREATE TABLE product_keywords (
  productid varchar(20) NOT NULL,
  keywords varchar(255) NOT NULL,
  PRIMARY KEY (productid,keywords),
  FOREIGN KEY (productid) REFERENCES product_details (productid)
) 

--
-- INSERT data for table product_keywords
--


INSERT INTO product_keywords VALUES ('PRD001', 'Note');
INSERT INTO product_keywords VALUES ('PRD001', 'Note20');
INSERT INTO product_keywords VALUES ('PRD001', 'Note20 Ultra');
INSERT INTO product_keywords VALUES ('PRD001', 'Phone');
INSERT INTO product_keywords VALUES ('PRD001', 'Samsung');
INSERT INTO product_keywords VALUES ('PRD001', 'Samsung Note20');
INSERT INTO product_keywords VALUES ('PRD002', 'Phone');
INSERT INTO product_keywords VALUES ('PRD002', 'Samsung');
INSERT INTO product_keywords VALUES ('PRD003', 'Keyboard');
INSERT INTO product_keywords VALUES ('PRD004', 'protector');
INSERT INTO product_keywords VALUES ('PRD004', 'Screen protector');
INSERT INTO product_keywords VALUES ('PRD005', 'iPhone');
INSERT INTO product_keywords VALUES ('PRD005', 'iPhone XS');
INSERT INTO product_keywords VALUES ('PRD005', 'iPhone XS Max');
INSERT INTO product_keywords VALUES ('PRD005', 'Phone');
INSERT INTO product_keywords VALUES ('PRD005', 'XS Max');
INSERT INTO product_keywords VALUES ('PRD006', 'Mouse');
INSERT INTO product_keywords VALUES ('PRD007', '5G');
INSERT INTO product_keywords VALUES ('PRD007', 'LG');
INSERT INTO product_keywords VALUES ('PRD007', 'LG Wing 5G');
INSERT INTO product_keywords VALUES ('PRD007', 'Phone');
INSERT INTO product_keywords VALUES ('PRD007', 'Wing 5G');
INSERT INTO product_keywords VALUES ('PRD008', 'Phone');
INSERT INTO product_keywords VALUES ('PRD008', 'S20');
INSERT INTO product_keywords VALUES ('PRD008', 'Samsung');
INSERT INTO product_keywords VALUES ('PRD008', 'Samsung S20');
INSERT INTO product_keywords VALUES ('PRD009', 'Phone');
INSERT INTO product_keywords VALUES ('PRD009', 'Samsung');
INSERT INTO product_keywords VALUES ('PRD010', 'fridge');
INSERT INTO product_keywords VALUES ('PRD010', 'fridges');
INSERT INTO product_keywords VALUES ('PRD011', 'laps');
INSERT INTO product_keywords VALUES ('PRD011', 'laptops');
INSERT INTO product_keywords VALUES ('PRD012', 'laps');
INSERT INTO product_keywords VALUES ('PRD012', 'laptops');
INSERT INTO product_keywords VALUES ('PRD013', 'washing machine');
INSERT INTO product_keywords VALUES ('PRD014', 'dryer');
INSERT INTO product_keywords VALUES ('PRD015', 'mixer');
INSERT INTO product_keywords VALUES ('PRD016', 'rice');
INSERT INTO product_keywords VALUES ('PRD017', 'blueshirt');
INSERT INTO product_keywords VALUES ('PRD017', 'shirt');
INSERT INTO product_keywords VALUES ('PRD018', 'shirt');
INSERT INTO product_keywords VALUES ('PRD019', 'shirts');
INSERT INTO product_keywords VALUES ('PRD020', 'ladies');
INSERT INTO product_keywords VALUES ('PRD021', 'yellow');
INSERT INTO product_keywords VALUES ('PRD022', 'ladies');
INSERT INTO product_keywords VALUES ('PRD023', 'jeans');
INSERT INTO product_keywords VALUES ('PRD024', 'red');
INSERT INTO product_keywords VALUES ('PRD025', 'green dress');
INSERT INTO product_keywords VALUES ('PRD026', 'green');
INSERT INTO product_keywords VALUES ('PRD027', 'yellow');
INSERT INTO product_keywords VALUES ('PRD028', 'blue');
INSERT INTO product_keywords VALUES ('PRD029', 'red');
INSERT INTO product_keywords VALUES ('PRD030', 'yellow');
INSERT INTO product_keywords VALUES ('PRD031', 'blue top');
INSERT INTO product_keywords VALUES ('PRD032', 'purple');
INSERT INTO product_keywords VALUES ('PRD033', 'chair');
INSERT INTO product_keywords VALUES ('PRD034', 'chairs');
INSERT INTO product_keywords VALUES ('PRD035', 'bed');
INSERT INTO product_keywords VALUES ('PRD035', 'matress');
INSERT INTO product_keywords VALUES ('PRD036', 'chairs');
INSERT INTO product_keywords VALUES ('PRD037', 'table');
INSERT INTO product_keywords VALUES ('PRD038', 'bed');
INSERT INTO product_keywords VALUES ('PRD039', 'chair');
INSERT INTO product_keywords VALUES ('PRD040', 'chair');
INSERT INTO product_keywords VALUES ('PRD040', 'table');
INSERT INTO product_keywords VALUES ('PRD041', 'wall');
INSERT INTO product_keywords VALUES ('PRD042', 'table');
INSERT INTO product_keywords VALUES ('PRD043', 'chair');
INSERT INTO product_keywords VALUES ('PRD044', 'table');
INSERT INTO product_keywords VALUES ('PRD045', 'table');
INSERT INTO product_keywords VALUES ('PRD046', 'chair');
INSERT INTO product_keywords VALUES ('PRD047', 'stands');
INSERT INTO product_keywords VALUES ('PRD048', 'chairs');
INSERT INTO product_keywords VALUES ('PRD049', 'soya');
INSERT INTO product_keywords VALUES ('PRD050', 'oreo');
INSERT INTO product_keywords VALUES ('PRD051', 'welch');
INSERT INTO product_keywords VALUES ('PRD052', 'lays');
INSERT INTO product_keywords VALUES ('PRD053', 'salt');
INSERT INTO product_keywords VALUES ('PRD054', 'salt');
INSERT INTO product_keywords VALUES ('PRD055', 'lays');
INSERT INTO product_keywords VALUES ('PRD056', 'mixture');
INSERT INTO product_keywords VALUES ('PRD057', 'doritos');
INSERT INTO product_keywords VALUES ('PRD058', 'soya');
INSERT INTO product_keywords VALUES ('PRD059', 'fritos');
INSERT INTO product_keywords VALUES ('PRD060', 'tea');
INSERT INTO product_keywords VALUES ('PRD061', 'rice');
INSERT INTO product_keywords VALUES ('PRD062', 'dalia');
INSERT INTO product_keywords VALUES ('PRD063', 'tea');
INSERT INTO product_keywords VALUES ('PRD064', 'colors');
INSERT INTO product_keywords VALUES ('PRD065', 'boy');
INSERT INTO product_keywords VALUES ('PRD066', 'girl');
INSERT INTO product_keywords VALUES ('PRD067', 'baby');
INSERT INTO product_keywords VALUES ('PRD067', 'kid');
INSERT INTO product_keywords VALUES ('PRD068', 'kidchair');
INSERT INTO product_keywords VALUES ('PRD069', 'cycle');
INSERT INTO product_keywords VALUES ('PRD070', 'panadol');
INSERT INTO product_keywords VALUES ('PRD071', 'basket');
INSERT INTO product_keywords VALUES ('PRD072', 'kids building toys');
INSERT INTO product_keywords VALUES ('PRD073', 'kids bag');
INSERT INTO product_keywords VALUES ('PRD074', 'kids food basket');
INSERT INTO product_keywords VALUES ('PRD075', 'cartoon kid bag');
INSERT INTO product_keywords VALUES ('PRD076', 'baby bag');
INSERT INTO product_keywords VALUES ('PRD077', 'kid chair little');
INSERT INTO product_keywords VALUES ('PRD078', 'kid pencil box');
INSERT INTO product_keywords VALUES ('PRD079', 'kid study box');
INSERT INTO product_keywords VALUES ('PRD080', 'kid bero');

-- --------------------------------------------------------

-- Table structure for table shop_details
--

CREATE TABLE shop_details (
  shopid varchar(20) NOT NULL PRIMARY KEY,
  shopName varchar(255) NOT NULL
) 

-- INSERT data for table shop_details
--


INSERT INTO shop_details VALUES ('SHP001', 'DressMart');
INSERT INTO shop_details VALUES ('SHP002', 'Tech World');
INSERT INTO shop_details VALUES ('SHP003', 'HomeNeeds');
INSERT INTO shop_details VALUES ('SHP004', 'GroceryWorld');
INSERT INTO shop_details VALUES ('SHP005', 'kidZone');

-- --------------------------------------------------------

--
-- Table structure for table shop_ownership
--

CREATE TABLE shop_ownership (
  shopid varchar(20) NOT NULL,
  ownerid varchar(20) NOT NULL PRIMARY KEY,
  FOREIGN KEY (shopid) REFERENCES shop_details (shopid),
  FOREIGN KEY (ownerid) REFERENCES user_details (userId)
) 

-- INSERT data for table shop_ownership
--

INSERT INTO shop_ownership  VALUES ('SHP001', 'SOW001');
INSERT INTO shop_ownership  VALUES ('SHP002', 'SOW002');
INSERT INTO shop_ownership  VALUES ('SHP003', 'SOW003');
INSERT INTO shop_ownership  VALUES ('SHP004', 'SOW004');
INSERT INTO shop_ownership  VALUES ('SHP005', 'SOW005');

-- --------------------------------------------------------

--
-- Table structure for table shop_products
--

CREATE TABLE shop_products (
  shopid varchar(20) NOT NULL,
  productID varchar(20) NOT NULL,
  PRIMARY KEY (shopid,productID),
  FOREIGN KEY (shopid) REFERENCES shop_details (shopid),
  FOREIGN KEY (productID) REFERENCES product_details (productid)
) 

--
-- INSERT data for table shop_products
--

INSERT INTO shop_products VALUES ('SHP001', 'PRD017');
INSERT INTO shop_products VALUES ('SHP001', 'PRD018');
INSERT INTO shop_products VALUES ('SHP001', 'PRD019');
INSERT INTO shop_products VALUES ('SHP001', 'PRD020');
INSERT INTO shop_products VALUES ('SHP001', 'PRD021');
INSERT INTO shop_products VALUES ('SHP001', 'PRD022');
INSERT INTO shop_products VALUES ('SHP001', 'PRD023');
INSERT INTO shop_products VALUES ('SHP001', 'PRD024');
INSERT INTO shop_products VALUES ('SHP001', 'PRD025');
INSERT INTO shop_products VALUES ('SHP001', 'PRD026');
INSERT INTO shop_products VALUES ('SHP001', 'PRD027');
INSERT INTO shop_products VALUES ('SHP001', 'PRD028');
INSERT INTO shop_products VALUES ('SHP001', 'PRD029');
INSERT INTO shop_products VALUES ('SHP001', 'PRD030');
INSERT INTO shop_products VALUES ('SHP001', 'PRD031');
INSERT INTO shop_products VALUES ('SHP001', 'PRD032');
INSERT INTO shop_products VALUES ('SHP002', 'PRD001');
INSERT INTO shop_products VALUES ('SHP002', 'PRD002');
INSERT INTO shop_products VALUES ('SHP002', 'PRD003');
INSERT INTO shop_products VALUES ('SHP002', 'PRD004');
INSERT INTO shop_products VALUES ('SHP002', 'PRD005');
INSERT INTO shop_products VALUES ('SHP002', 'PRD006');
INSERT INTO shop_products VALUES ('SHP002', 'PRD007');
INSERT INTO shop_products VALUES ('SHP002', 'PRD008');
INSERT INTO shop_products VALUES ('SHP002', 'PRD009');
INSERT INTO shop_products VALUES ('SHP002', 'PRD010');
INSERT INTO shop_products VALUES ('SHP002', 'PRD011');
INSERT INTO shop_products VALUES ('SHP002', 'PRD012');
INSERT INTO shop_products VALUES ('SHP002', 'PRD013');
INSERT INTO shop_products VALUES ('SHP002', 'PRD014');
INSERT INTO shop_products VALUES ('SHP002', 'PRD015');
INSERT INTO shop_products VALUES ('SHP002', 'PRD016');
INSERT INTO shop_products VALUES ('SHP003', 'PRD033');
INSERT INTO shop_products VALUES ('SHP003', 'PRD034');
INSERT INTO shop_products VALUES ('SHP003', 'PRD035');
INSERT INTO shop_products VALUES ('SHP003', 'PRD036');
INSERT INTO shop_products VALUES ('SHP003', 'PRD037');
INSERT INTO shop_products VALUES ('SHP003', 'PRD038');
INSERT INTO shop_products VALUES ('SHP003', 'PRD039');
INSERT INTO shop_products VALUES ('SHP003', 'PRD040');
INSERT INTO shop_products VALUES ('SHP003', 'PRD041');
INSERT INTO shop_products VALUES ('SHP003', 'PRD042');
INSERT INTO shop_products VALUES ('SHP003', 'PRD043');
INSERT INTO shop_products VALUES ('SHP003', 'PRD044');
INSERT INTO shop_products VALUES ('SHP003', 'PRD045');
INSERT INTO shop_products VALUES ('SHP003', 'PRD046');
INSERT INTO shop_products VALUES ('SHP003', 'PRD047');
INSERT INTO shop_products VALUES ('SHP003', 'PRD048');
INSERT INTO shop_products VALUES ('SHP004', 'PRD049');
INSERT INTO shop_products VALUES ('SHP004', 'PRD050');
INSERT INTO shop_products VALUES ('SHP004', 'PRD051');
INSERT INTO shop_products VALUES ('SHP004', 'PRD052');
INSERT INTO shop_products VALUES ('SHP004', 'PRD053');
INSERT INTO shop_products VALUES ('SHP004', 'PRD054');
INSERT INTO shop_products VALUES ('SHP004', 'PRD055');
INSERT INTO shop_products VALUES ('SHP004', 'PRD056');
INSERT INTO shop_products VALUES ('SHP004', 'PRD057');
INSERT INTO shop_products VALUES ('SHP004', 'PRD058');
INSERT INTO shop_products VALUES ('SHP004', 'PRD059');
INSERT INTO shop_products VALUES ('SHP004', 'PRD060');
INSERT INTO shop_products VALUES ('SHP004', 'PRD061');
INSERT INTO shop_products VALUES ('SHP004', 'PRD062');
INSERT INTO shop_products VALUES ('SHP004', 'PRD063');
INSERT INTO shop_products VALUES ('SHP004', 'PRD064');
INSERT INTO shop_products VALUES ('SHP005', 'PRD065');
INSERT INTO shop_products VALUES ('SHP005', 'PRD066');
INSERT INTO shop_products VALUES ('SHP005', 'PRD067');
INSERT INTO shop_products VALUES ('SHP005', 'PRD068');
INSERT INTO shop_products VALUES ('SHP005', 'PRD069');
INSERT INTO shop_products VALUES ('SHP005', 'PRD070');
INSERT INTO shop_products VALUES ('SHP005', 'PRD071');
INSERT INTO shop_products VALUES ('SHP005', 'PRD072');
INSERT INTO shop_products VALUES ('SHP005', 'PRD073');
INSERT INTO shop_products VALUES ('SHP005', 'PRD074');
INSERT INTO shop_products VALUES ('SHP005', 'PRD075');
INSERT INTO shop_products VALUES ('SHP005', 'PRD076');
INSERT INTO shop_products VALUES ('SHP005', 'PRD077');
INSERT INTO shop_products VALUES ('SHP005', 'PRD078');
INSERT INTO shop_products VALUES ('SHP005', 'PRD079');
INSERT INTO shop_products VALUES ('SHP005', 'PRD080');

-- --------------------------------------------------------

-- Table structure for table wishlist_user
--

CREATE TABLE wishlist_user (
  wishlistid varchar(20) NOT NULL PRIMARY KEY,
  userid varchar(20) NOT NULL,
  FOREIGN KEY (userid) REFERENCES user_details (userId)
) 

INSERT INTO wishlist_user VALUES ('WSH001', 'CMR006');
INSERT INTO wishlist_user VALUES ('WSH002', 'SOW001');
INSERT INTO wishlist_user VALUES ('WSH003', 'CMR001');
INSERT INTO wishlist_user VALUES ('WSH004', 'CMR002');
INSERT INTO wishlist_user VALUES ('WSH005', 'CMR003');

-- Table structure for table wishlist_products
--

CREATE TABLE wishlist_products (
  wishlistid varchar(20) NOT NULL,
  productid varchar(20) NOT NULL,
  PRIMARY KEY (wishlistid,productid),
  FOREIGN KEY (productid) REFERENCES product_details (productid),
  FOREIGN KEY (wishlistid) REFERENCES wishlist_user (wishlistid)
) 

INSERT INTO wishlist_products VALUES ('WSH001', 'PRD003');
INSERT INTO wishlist_products VALUES ('WSH001', 'PRD008');
INSERT INTO wishlist_products VALUES ('WSH001', 'PRD009');
INSERT INTO wishlist_products VALUES ('WSH002', 'PRD005');
INSERT INTO wishlist_products VALUES ('WSH002', 'PRD009');
INSERT INTO wishlist_products VALUES ('WSH002', 'PRD011');

-- --------------------------------------------------------


CREATE TABLE cart_user (
  cartId varchar(20) NOT NULL PRIMARY KEY,
  userID varchar(20) NOT NULL,
  FOREIGN KEY (userID) REFERENCES user_details (userId)
) 


INSERT INTO cart_user VALUES ('CRT002', 'CMR006');
INSERT INTO cart_user VALUES('CRT001', 'SOW002');
INSERT INTO cart_user VALUES ('CRT003', 'CMR001');
INSERT INTO cart_user VALUES ('CRT004', 'CMR002');
INSERT INTO cart_user VALUES ('CRT005', 'CMR003');

-- --------------------------------------------------------

CREATE TABLE cart_products (
  cartId varchar(20) NOT NULL,
  productID varchar(20) NOT NULL,
  cartquantity INTEGER NOT NULL,
  cartcolor varchar(255) NOT NULL DEFAULT 'None',
  PRIMARY KEY (cartId,productID,cartcolor),
  FOREIGN KEY (cartId) REFERENCES cart_user (cartId),
  FOREIGN KEY (productID) REFERENCES product_details (productid)
) 


-- INSERT data for table cart_products


INSERT INTO cart_products VALUES ('CRT001', 'PRD005', 1, 'black');
INSERT INTO cart_products VALUES ('CRT001', 'PRD005', 4, 'red');
INSERT INTO cart_products VALUES ('CRT001', 'PRD016', 1, 'None');
INSERT INTO cart_products VALUES ('CRT002', 'PRD003', 1, 'black');
INSERT INTO cart_products VALUES ('CRT002', 'PRD010', 1, 'silver');


-- Table structure for table `payment_details`
--

CREATE TABLE payment_details (
  paymentId varchar(20) NOT NULL PRIMARY KEY,
  amount Decimal(10,2) NOT NULL
) 

---- Dumping data for table `payment_details`
--

INSERT INTO payment_details VALUES ('PMT001', '1000.00');
INSERT INTO payment_details VALUES ('PMT002', '21120.00');
INSERT INTO payment_details VALUES ('PMT003', '1000.00');
INSERT INTO payment_details VALUES ('PMT004', '211520.00');
INSERT INTO payment_details VALUES ('PMT005', '10400.00');
INSERT INTO payment_details VALUES ('PMT006', '213120.00');

-- Table structure for table order_details
--

CREATE TABLE order_details (
  orderId varchar(20) NOT NULL PRIMARY KEY,
  orderDate DATETIME NOT NULL DEFAULT CURRENT_TIMESTAMP, 
  customerID varchar(20) NOT NULL,
  paymentId varchar(20) NOT NULL,
  FOREIGN KEY (customerID) REFERENCES user_details (userId),
  FOREIGN KEY (paymentId) REFERENCES payment_details (paymentId)
) 

SELECT * FROM order_details

-- INSERT data for table order_details
--

INSERT INTO order_details (orderId, customerID,paymentId) VALUES ('ORD001', 'CMR001', 'PMT001');
INSERT INTO order_details VALUES ('ORD002', '2020-10-14 13:38:33', 'CMR002', 'PMT002')
INSERT INTO order_details VALUES ('ORD003', '2020-10-15 13:38:33', 'CMR001', 'PMT003')
INSERT INTO order_details VALUES ('ORD004', '2020-10-16 13:38:33', 'CMR005', 'PMT004')
INSERT INTO order_details VALUES ('ORD005', '2020-10-17 13:38:33', 'CMR003', 'PMT005')
INSERT INTO order_details VALUES ('ORD006', '2020-10-18 13:38:33', 'CMR002', 'PMT006')


-- --------------------------------------------------------
--
-- Table structure for table order_products
--

CREATE TABLE order_products (
  orderId varchar(20) NOT NULL,
  productID varchar(20) NOT NULL,
  ordquantity INTEGER NOT NULL,
  ordcolor varchar(255) NOT NULL DEFAULT 'None',
  ordstatus varchar(30) NOT NULL DEFAULT 'Processing',
  customerview varchar(30) NOT NULL DEFAULT 'Show',
  PRIMARY KEY (orderId,productID,ordcolor),
  FOREIGN KEY (orderId) REFERENCES order_details (orderId),
  FOREIGN KEY (productID) REFERENCES product_details (productid)
) 


--
-- INSERT data for table order_products
--

INSERT INTO order_products (orderId, productID, ordquantity, ordcolor, ordstatus) VALUES ('ORD001', 'PRD002', 15, 'None', 'shipped');
INSERT INTO order_products VALUES ('ORD002', 'PRD003', 21, 'None', 'Processing', 'Show');
INSERT INTO order_products VALUES ('ORD002', 'PRD005', 4, 'None', 'shipped', 'Show');
INSERT INTO order_products VALUES ('ORD003', 'PRD008', 1, 'None', 'Processing', 'Show');
INSERT INTO order_products VALUES ('ORD003', 'PRD001', 6, 'None', 'shipped', 'Show');
INSERT INTO order_products VALUES ('ORD004', 'PRD002', 2, 'None', 'Processing', 'Show');
INSERT INTO order_products VALUES ('ORD005', 'PRD006', 1, 'None', 'shipped', 'Show');
INSERT INTO order_products VALUES ('ORD005', 'PRD007', 2, 'None', 'Processing', 'Show');
INSERT INTO order_products VALUES ('ORD006', 'PRD009', 4, 'None', 'shipped', 'Show');
INSERT INTO order_products VALUES ('ORD006', 'PRD010', 5, 'None', 'Processing', 'Show');


-- --------------------------------------------------------