# MyBatis

```xml
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE mapper PUBLIC "-//mybatis.org//DTD Mapper 3.0//EN" "http://mybatis.org/dtd/mybatis-3-mapper.dtd" >
<mapper namespace="com.qianyan.dao.SiteDao">
    <insert id="insertOrderInfo" parameterType="com.qianyan.domain.Order" useGeneratedKeys="true" keyProperty="id">INSERT INTO `mi_order`(`out_trade_no`, `userid`)VALUES(#{outTradeNo}, #{userid})</insert>
    <insert id="batchSaveLabelUser" parameterType="java.util.List">
        INSERT INFO mi_order (out_trade_no, userid) VALUES
        <foreach collection="orders" item="order" index="index" separator=",">
            (#{order.outTradeNo}, #{order.userid})
        </foreach>
    </insert>

    <select id="getOrderListByPage" parameterType="com.qianyan.domain.query.OrderQuery" resultType="com.qianyan.domain.Order">
        SELECT * FROM `mi_order`
        <where>
            <if test="userid != null">
                AND `userid` = #{userid}
            </if>
            <if test="siteId != null">
                AND `site_id` = #{siteId}
            </if>
            <if test="resiteId != null">
                AND `resite_id` = #{resiteId}
            </if>
            <if test="useState != null">
                AND `use_state` = #{useState}
            </if>
        </where>
        ORDER BY `id` DESC LIMIT #{start}, #{num}
    </select>

    <select id="getSiteListByKeyword" parameterType="com.qianyan.domain.query.SiteQuery" resultType="com.qianyan.domain.Site">
        SELECT `id`, `name`, `uuid`, `pos_num`, `mch_id`, `province_id`, `city_id`, `area_id`, `address`, `longitude`, `latitude`, `net_type`, `status`, `stock_status`, `up_status` FROM `mi_site`
        <where>
            <if test="id != null">`id` LIKE CONCAT('%', #{id}, '%')</if>
            <if test="name != null">OR `name` LIKE CONCAT('%', #{name}, '%')</if>
            <if test="uuid != null">OR `uuid` LIKE CONCAT('%', #{uuid}, '%')</if>
        </where>
        ORDER BY `id` DESC LIMIT #{start}, #{num}
    </select>

    <select id="selectNums" resultType="int">select count(*) from tableName</select>

    <update id="updateOrderInfoById" parameterType="com.qianyan.domain.Order">
        UPDATE `ch_order`
        <set>
            <if test="posId != null">`pos_id` = #{posId},</if>
            <if test="identifier != null">`identifier` = #{identifier},</if>
            <if test="power != null">`power` = #{power},</if>
            <if test="free != null">`free` = #{free},</if>
            <if test="couponId != null">`coupon_id` = #{couponId},</if>
            <if test="type != null">`type` = #{type},</if>
            <if test="getMoney != null">`get_money` = #{getMoney},</if>
            <if test="useState != null">`use_state` = #{useState},</if>
            <if test="stockStatus != null">`stock_status` = #{stockStatus},</if>
            <if test="resiteId != null">`resite_id` = #{resiteId},</if>
            <if test="resiteName != null">`resite_name` = #{resiteName},</if>
            <if test="reposId != null">`repos_id` = #{reposId},</if>
            <if test="borrowTime != null">`borrow_time` = #{borrowTime},</if>
            <if test="restoreTime != null">`restore_time` = #{restoreTime},</if>
            <if test="updateTime != null">`update_time` = #{updateTime},</if>
        </set>
        WHERE `id` = #{id}
    </update>

    <delete id="deleteOrderInfoById" parameterType="int", resultType="int">DELETE FROM `ch_order` WHERE `id` = #{id}</delete>
</mapper>
```

